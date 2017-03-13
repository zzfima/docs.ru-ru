---
title: "Практическое руководство. Использование вызова неуправляемого кода для воспроизведения звукового файла (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "WAV-файлы"
  - "взаимодействие [C#], воспроизведение WAV-файлов с использованием метода pinvoke"
  - "вызов неуправляемого кода, звуковые файл"
  - "WAV-файлы"
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Практическое руководство. Использование вызова неуправляемого кода для воспроизведения звукового файла (Руководство по программированию на C#)
В следующем примере кода демонстрируется использование служб вызова неуправляемого кода для воспроизведения звукового файла в операционной системе Windows.  
  
## Пример  
 В данном примере кода `DllImport` используется для импорта точки входа метода `PlaySound` `winmm.dll` в качестве `Form1 PlaySound()`.  В примере используется простая форма Windows с кнопкой.  При нажатии кнопки открывается стандартное диалоговое окно Windows <xref:System.Windows.Forms.OpenFileDialog>, в котором можно выбрать воспроизводимый файл.  Когда звуковой файл выбран, он воспроизводится с помощью метода `PlaySound()` из метода сборки winmm.DLL.  Дополнительные сведения о методе `PlaySound` библиотеки winmm.dll см. в статье [Использование функции PlaySound с файлами формата Waveform\-Audio](http://go.microsoft.com/fwlink/?LinkId=148553).  Найдите и выберите файл с расширением .wav, а затем нажмите кнопку **Открыть** для воспроизведения звукового файла с помощью вызова неуправляемого кода.  В текстовом поле отображается полный путь к выбранному файлу.  
  
 В диалоговом окне **Открытые файлы** отображаются только файлы, имеющие расширение .wav, так как в нем действуют параметры фильтра:  
  
 [!code-cs[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-cs[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## Компиляция кода  
  
### Чтобы скомпилировать этот код, выполните следующие действия.  
  
1.  Создайте в Visual Studio новый проект приложения Windows C\# и назовите его WinSound.  
  
2.  Скопируйте приведенный выше код и вставьте его поверх содержимого файла `Form1.cs`.  
  
3.  Скопируйте следующий код и вставьте его в файл `Form1.Designer.cs` в метод `InitializeComponent()` после уже имеющегося там кода.  
  
     [!code-cs[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  Скомпилируйте и запустите код.  
  
## Безопасность платформы .NET Framework  
 Дополнительные сведения см. в разделе [Безопасность .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Общие сведения о взаимодействии](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [Общие сведения о взаимодействии](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [A Closer Look at Platform Invoke](http://msdn.microsoft.com/ru-ru/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)   
 [Marshaling Data with Platform Invoke](../Topic/Marshaling%20Data%20with%20Platform%20Invoke.md)