---
title: Использование метода Async для доступа к файлам (C#)
ms.date: 07/20/2015
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
ms.openlocfilehash: e6b0370049d9b9315de6a72d0e84c080aac12481
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595545"
---
# <a name="using-async-for-file-access-c"></a>Использование метода Async для доступа к файлам (C#)
Для доступа к файлам можно использовать функцию Async. При использовании функции Async вы можете вызывать асинхронные методы без использования обратных вызовов или разделения вашего кода на множество методов или лямбда-выражений. Для выполнения последовательного кода асинхронно просто вызовите асинхронный метод вместо синхронного метода и добавьте несколько ключевых слов в код.  
  
 Можно рассмотреть следующие причины для добавления асинхронности для вызовов для доступа к файлам.  
  
- Асинхронность делает приложения пользовательского интерфейса более отзывчивыми, потому что поток пользовательского интерфейса, который запускает операцию, может продолжать выполнять и другую работу. Если поток пользовательского интерфейса должен выполнять код, который занимает много времени (например, более 50 миллисекунд), пользовательский интерфейс можно приостановить до тех пор, пока не будет завершен ввод-вывод, и затем пользовательский интерфейс сможет снова обрабатывать ввод с клавиатуры, мыши и другие события.  
  
- Асинхронность улучшает масштабируемость ASP.NET и других серверных приложений за счет уменьшения необходимости использования потоков. Если приложение использует выделенный поток на ответ и тысяча запросов приходит одновременно, тысяча потоков не потребуется. Асинхронные операции часто не нуждаются в пользовании потоком во время ожидания. Они пользуются существующим потоком завершения ввода-вывода короткое время в конце.  
  
- Задержка операции доступа к файлу может быть очень низкой при текущих условиях, но может значительно увеличиться в будущем. Например, файл может быть перемещен на сервер через Интернет.  
  
- Добавленные издержки при использовании функции Async являются малыми.  
  
- Асинхронные задачи могут легко выполняться параллельно.  
  
## <a name="running-the-examples"></a>Выполнение примеров  
 Чтобы выполнить примеры в этом разделе, вы можете создать **приложение WPF** или **приложение Windows Forms**, а затем добавить **кнопку**. В событии `Click` кнопки добавьте вызов к первому методу в каждом примере.  
  
 В следующие примеры добавьте указанные ниже операторы`using`.  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Diagnostics;  
using System.IO;  
using System.Text;  
using System.Threading.Tasks;  
```  
  
## <a name="use-of-the-filestream-class"></a>Использование класса FileStream  
 В приведенных в этой статье примерах используется класс <xref:System.IO.FileStream>, содержащий параметр, который вызывает асинхронный ввод-вывод на уровне операционной системы. С помощью этого параметра можно избежать блокирования пула потоков во многих случаях. Чтобы включить этот параметр, необходимо добавить в вызов конструктора аргумент `useAsync=true` или `options=FileOptions.Asynchronous`.  
  
 Этот параметр нельзя использовать с классами <xref:System.IO.StreamReader> и <xref:System.IO.StreamWriter>, если вы открываете их напрямую (указав путь к файлу). При этом параметр можно использовать, если им предоставлен <xref:System.IO.Stream>, открытый классом <xref:System.IO.FileStream>. Обратите внимание, что асинхронные вызовы выполняются быстрее в приложениях пользовательского интерфейса, даже если поток в пуле потоков блокирован, поскольку поток пользовательского интерфейса не блокирован во время ожидания.  
  
## <a name="writing-text"></a>Запись текста  
 Следующие примеры записывают текст в файл. На каждой точке await происходит немедленный выход из метода. После завершения файлового ввода-вывода метод возобновляет работу с пункта, следующего за await. Обратите внимание, что модификатор async в определении методов требует наличия await в теле метода.  
  
```csharp  
public async Task ProcessWriteAsync()  
{  
    string filePath = @"temp2.txt";  
    string text = "Hello World\r\n";  
  
    await WriteTextAsync(filePath, text);  
}  
  
private async Task WriteTextAsync(string filePath, string text)  
{  
    byte[] encodedText = Encoding.Unicode.GetBytes(text);  
  
    using (FileStream sourceStream = new FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize: 4096, useAsync: true))  
    {  
        await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
    };  
}  
```  
  
 Первоначальная строка с оператором `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);` является сокращенной формой записи двух следующих операторов:  
  
```csharp  
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
await theTask;  
```  
  
 Первый оператор возвращает задачу и вызывает запуск обработки файла. Вторая строка с await немедленно оставляет метод и возвращается в другую задачу. При окончании обработки файла выполнение возвращается в точку выполнения, которая следует за await. Дополнительные сведения см. в разделе [Поток управления в асинхронных программах (C#)](./control-flow-in-async-programs.md).  
  
## <a name="reading-text"></a>Чтение текста  
 Следующий пример считывает текст из файла. Текст добавляется в буфер обмена, а затем, в данном случае, помещается в <xref:System.Text.StringBuilder>. В отличие от предыдущего примера await выдаёт в результате значение. Метод <xref:System.IO.Stream.ReadAsync%2A> возвращает <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, поэтому по завершении операции оценка await выдает значение `Int32` (`numRead`). Дополнительные сведения см. в разделе [Асинхронные типы возвращаемых значений (C#)](./async-return-types.md).  
  
```csharp  
public async Task ProcessReadAsync()  
{  
    string filePath = @"temp2.txt";  
  
    if (File.Exists(filePath) == false)  
    {  
        Debug.WriteLine("file not found: " + filePath);  
    }  
    else  
    {  
        try  
        {  
            string text = await ReadTextAsync(filePath);  
            Debug.WriteLine(text);  
        }  
        catch (Exception ex)  
        {  
            Debug.WriteLine(ex.Message);  
        }  
    }  
}  
  
private async Task<string> ReadTextAsync(string filePath)  
{  
    using (FileStream sourceStream = new FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize: 4096, useAsync: true))  
    {  
        StringBuilder sb = new StringBuilder();  
  
        byte[] buffer = new byte[0x1000];  
        int numRead;  
        while ((numRead = await sourceStream.ReadAsync(buffer, 0, buffer.Length)) != 0)  
        {  
            string text = Encoding.Unicode.GetString(buffer, 0, numRead);  
            sb.Append(text);  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
## <a name="parallel-asynchronous-io"></a>Параллельный асинхронный ввод-вывод  
 В следующем примере показана параллельная обработка при записи 10 текстовых файлов. Для каждого файла метод <xref:System.IO.Stream.WriteAsync%2A> возвращает задачу, которая затем добавляется в список задач. Оператор `await Task.WhenAll(tasks);` существует и возобновляется в методе, как только завершается обработка файла для всех задач.  
  
 Пример закрывает все экземпляры <xref:System.IO.FileStream> в блоке `finally` после завершения всех задач. Если бы вместо этого каждый `FileStream` был бы создан в операторе `using`, то `FileStream` можно было бы удалить до завершения задачи.  
  
 Обратите внимание, что любое увеличение производительности зависит почти полностью от параллельной, а не асинхронной обработки. Преимущества асинхронности в том, что она не привязана к количеству потоков и не связана с потоком пользовательского интерфейса.  
  
```csharp  
public async Task ProcessWriteMultAsync()  
{  
    string folder = @"tempfolder\";  
    List<Task> tasks = new List<Task>();  
    List<FileStream> sourceStreams = new List<FileStream>();  
  
    try  
    {  
        for (int index = 1; index <= 10; index++)  
        {  
            string text = "In file " + index.ToString() + "\r\n";  
  
            string fileName = "thefile" + index.ToString("00") + ".txt";  
            string filePath = folder + fileName;  
  
            byte[] encodedText = Encoding.Unicode.GetBytes(text);  
  
            FileStream sourceStream = new FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize: 4096, useAsync: true);  
  
            Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
            sourceStreams.Add(sourceStream);  
  
            tasks.Add(theTask);  
        }  
  
        await Task.WhenAll(tasks);  
    }  
  
    finally  
    {  
        foreach (FileStream sourceStream in sourceStreams)  
        {  
            sourceStream.Close();  
        }  
    }  
}  
```  
  
 При использовании методов <xref:System.IO.Stream.WriteAsync%2A> и <xref:System.IO.Stream.ReadAsync%2A> можно указать <xref:System.Threading.CancellationToken>, который позволяет отменить операцию в середине потока. Дополнительные сведения см. в разделах [Настройка асинхронного приложения (C#)](./fine-tuning-your-async-application.md) и [Отмена в управляемых потоках](../../../../standard/threading/cancellation-in-managed-threads.md).  
  
## <a name="see-also"></a>См. также раздел

- [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](./index.md)
- [Async Return Types (C#)](./async-return-types.md) (Типы возвращаемых значений асинхронных операций в C#)
- [Поток управления в асинхронных программах (C#)](./control-flow-in-async-programs.md)
