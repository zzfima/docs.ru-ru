---
title: "Walkthrough: Creating a Dataflow Pipeline | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dataflow pipelines, creating with TPL"
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, creating dataflow pipeline"
ms.assetid: 69308f82-aa22-4ac5-833d-e748533b58e8
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Walkthrough: Creating a Dataflow Pipeline
Хотя можно использовать методы <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A?displayProperty=fullName> и <xref:System.Threading.Tasks.Dataflow.DataflowBlock.TryReceive%2A?displayProperty=fullName>, чтобы получать сообщения из блоков источника, можно также соединять блоки сообщений для формирования *конвейера потока данных*.  Конвейер потока данных — это цепочка компонентов, или *блоков потока данных*, каждый из которых выполняет конкретную задачу в рамках более крупной цели.  Каждый блок потока данных в конвейере потока данных выполняет работу, когда получает сообщение от другого блока потока данных.  Можно сравнить это с линией сборки автомобилей.  Как при продвижении автомобиля по сборочной линии одна станция собирает раму, следующая — устанавливает двигатель и так далее.  Так как при этом можно собирать одновременно много автомобилей, линия сборки обеспечивает большую производительность, чем полная сборка автомобилей по одному.  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Для установки пространства имен <xref:System.Threading.Tasks.Dataflow> откройте свой проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Управление пакетами NuGet** в меню "Проект" и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
 В этом документе демонстрируется конвейер потока данных, который загружает книгу *«Илиада» Гомера* с веб\-сайта и выполняет поиск в тексте  для сопоставления отдельных слов со словами, в которых переставлены первые символы слова.  Формирование конвейера потока данных в этом документе состоит из следующих шагов.  
  
1.  Создание блоков потока данных, которые участвуют в конвейере.  
  
2.  Подсоединение каждого блока потока данных к следующему блоку в конвейере.  Каждый блок получает в качестве входных данных выходные данные предыдущего блока в конвейере.  
  
3.  Для каждого блока потока данных создайте задачу продолжения, которая переводит следующий блок в завершенное состояние, после того как заканчивается выполнение предыдущего блока.  
  
4.  Отправьте данные в начало конвейера.  
  
5.  Пометьте начало конвейера как завершенное.  
  
6.  Подождите, пока конвейер не завершит всю работу.  
  
## Обязательные компоненты  
 Прежде чем приступить к данному пошаговому руководству, прочтите статью [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
## Создание консольного приложения  
 В [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] создайте новый проект консольного приложения [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] или [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].  Добавьте ссылку на System.Threading.Tasks.Dataflow.dll.  
  
 Также можно создать файл с именем `ReverseWords.cs` \(`ReverseWords.vb` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), а затем выполнить следующую команду в окне командной строки Visual Studio, чтобы скомпилировать проект.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll ReverseWords.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll ReverseWords.vb**  
  
 Добавьте следующий код в проект для создания простого приложения.  
  
 [!code-csharp[TPLDataflow_Palindromes#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#2)]
 [!code-vb[TPLDataflow_Palindromes#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#2)]  
  
## Создание блоков потоков данных  
 Добавьте следующий код в метод `Main` для создания блоков потока данных, которые участвуют в конвейере.  Таблица ниже описывает роль каждой части конвейера.  
  
 [!code-csharp[TPLDataflow_Palindromes#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#3)]
 [!code-vb[TPLDataflow_Palindromes#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#3)]  
  
|Член|Тип|Описание|  
|----------|---------|--------------|  
|`downloadString`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Загружает текст книги из Интернета.|  
|`createWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Разбивает текст книги на массив слов.|  
|`filterWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Удаляет короткие слова из массива слов, упорядочивает оставшиеся слова в алфавитном порядке и удаляет дубликаты.|  
|`findReversedWords`|<xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>|Находит все слова в отфильтрованной коллекции массива слов, которые также встречаются в массиве слов с обратным порядком символов.|  
|`printReversedWords`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Выводит на консоль слова и соответствующие обратные слова.|  
  
 Хотя можно объединить несколько шагов конвейера потока данных в этом примере в один шаг, на примере демонстрируется концепция создания нескольких независимых задач потока данных для выполнения более крупной задачи.  В примере используется <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, чтобы позволить каждой части конвейера выполнить операцию с ее входными данными и отправить результат на следующий этап конвейера.  Часть конвейера `findReversedWords` — это объект <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>, поскольку он создает несколько независимых выходных данных для каждого входного значения.  Конец конвейера, `printReversedWords`, — это объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, так как он выполняет действие со входными данными и не создает выходных данных.  
  
## Формирование конвейера  
 Добавьте следующий код, чтобы подсоединить каждый блок к следующему блоку конвейера.  
  
 При вызове метода <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> для подсоединения блока потока данных источника к блоку потока данных целевого объекта, блок потока данных источника передает данные блокам целевых объектов, как только данные становятся доступны.  
  
 [!code-csharp[TPLDataflow_Palindromes#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#4)]
 [!code-vb[TPLDataflow_Palindromes#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#4)]  
  
## Создание задач завершения  
 Добавьте следующий код, чтобы каждый блок потока данных мог выполнять заключительное действие после обработки всех данных.  
  
 [!code-csharp[TPLDataflow_Palindromes#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#5)]
 [!code-vb[TPLDataflow_Palindromes#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#5)]  
  
 Для передачи информации о завершении по конвейеру каждая задача завершения переводит следующий блок потока данных в завершенное состояние.  Например, если начало конвейера переводится в состояние завершения, оно обрабатывает все оставшиеся буферизованные сообщения и запускает задачу завершения, которая переводит вторую часть конвейера в состояние завершения.  Вторая часть конвейера, в свою очередь, обрабатывает все оставшиеся буферизованные сообщение и запускает задачу завершения, которая переводит третью часть конвейера в состояние завершения.  Этот процесс продолжается до тех пор, пока все части конвейера не завершат работу.  В этом примере используется ключевое слово `delegate` \(`Function` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) для определения задач продолжения.  
  
## Передача данных в конвейере  
 Добавьте следующий код для помещения url\-адреса книги *"Илиада" Гомера* в начало конвейера потока данных.  
  
 [!code-csharp[TPLDataflow_Palindromes#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#6)]
 [!code-vb[TPLDataflow_Palindromes#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#6)]  
  
 В этом примере используется <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A?displayProperty=fullName> для синхронной отправки данных в начало конвейера.  Используйте метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A?displayProperty=fullName> при необходимости асинхронной отправки данных в узел потока данных.  
  
## Завершение работы конвейера  
 Добавьте следующий код, чтобы пометить начало конвейера как завершенное.  Начало конвейера выполняет свою задачу продолжения после обработки всех буферизованных сообщений.  Эта задача продолжения передает состояние завершения по конвейеру.  
  
 [!code-csharp[TPLDataflow_Palindromes#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#7)]
 [!code-vb[TPLDataflow_Palindromes#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#7)]  
  
 Этот пример отправляет один url\-адрес через конвейер потока данных для обработки.  Если на вход подается более одного элемента данных, вызовите метод <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A?displayProperty=fullName> после передачи всех входных данных.  Этот шаг можно пропустить, если в вашем приложении нет определенной точки, в которой данные более недоступны или приложение не должно ожидать завершения работы конвейера.  
  
## Ожидание завершения работы конвейера  
 Добавьте следующий код, чтобы ожидать завершения работы конвейера.  Поскольку в этом примере используются задачи продолжения для передачи состояния завершения по конвейеру, общая операция завершится, когда завершит работу конец конвейера.  
  
 [!code-csharp[TPLDataflow_Palindromes#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#8)]
 [!code-vb[TPLDataflow_Palindromes#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#8)]  
  
 Можно ожидать завершения потока данных из любого потока или из нескольких потоков одновременно.  
  
## Полный пример  
 В следующем примере приведен полный код для этого руководства.  
  
 [!code-csharp[TPLDataflow_Palindromes#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#1)]
 [!code-vb[TPLDataflow_Palindromes#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#1)]  
  
## Следующие действия  
 В этом примере один url\-адрес отправляется на обработку через конвейер потока данных.  Если через конвейер отправляется более одного входного значения, можно внедрить в приложении форму параллелизма, которая напоминает перемещение деталей по автомобильному заводу.  Когда первая часть конвейера отправляет свой результат второй части, она может обрабатывать другой элемент параллельно с тем, как вторая часть обрабатывает первый результат.  
  
 Параллелизм, полученный с помощью конвейеров потока данных, известен как *грубый параллелизм*, поскольку он обычно состоит из небольшого количества крупных задач.  Можно также использовать более *точный параллелизм* из меньших быстро выполняемых задач в конвейере потока данных.  В этом примере часть конвейера `findReversedWords` использует метод <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> для параллельной обработки нескольких элементов в списке работ.  Использование точного параллелизма в конвейере с несколькими крупными функциями может повысить общую пропускную способность.  
  
 Можно также подсоединить блок потока данных источника к нескольким целевым блокам для создания *сети потока данных*.  Перегруженная версия метода <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> принимает объект <xref:System.Predicate%601>, который определяет, примет ли целевой объект сообщение, основываясь на его значении.  Большинство типов блоков потока данных, выполняющих роль источников, предлагают сообщения всем подключенным целевым блокам в порядке их подсоединения, пока один из блоков не примет это сообщение.  С помощью этого механизма фильтрации можно создавать системы связанных блоков потока данных, которые будут направлять определенные по одному пути, а другие данные — по другому пути.  Пример использования фильтрации для создания сети потока данных, см. в разделе [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)