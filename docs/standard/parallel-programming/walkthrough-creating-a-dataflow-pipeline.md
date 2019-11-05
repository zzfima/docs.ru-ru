---
title: Пошаговое руководство. Создание конвейера потока данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow pipelines, creating with TPL
- Task Parallel Library, dataflows
- TPL dataflow library, creating dataflow pipeline
ms.assetid: 69308f82-aa22-4ac5-833d-e748533b58e8
ms.openlocfilehash: 284be7789b6411055a6421fd07cc1b0605f6ea0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139870"
---
# <a name="walkthrough-creating-a-dataflow-pipeline"></a>Пошаговое руководство. Создание конвейера потока данных
Чтобы получать сообщения из блоков источника, можно использовать методы <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Dataflow.DataflowBlock.TryReceive%2A?displayProperty=nameWithType> или же объединить блоки сообщений в *конвейер потока данных*. Конвейер потока данных — это цепочка компонентов, или *блоков потока данных*, каждый из которых выполняет конкретную задачу в рамках более крупной цели. Каждый блок потока данных в конвейере потока данных выполняет работу, когда получает сообщение от другого блока потока данных. Можно сравнить это с линией сборки автомобилей. Как при продвижении автомобиля по сборочной линии одна станция собирает раму, следующая — устанавливает двигатель и так далее. Так как при этом можно собирать одновременно много автомобилей, линия сборки обеспечивает большую производительность, чем полная сборка автомобилей по одному.

 В этом документе демонстрируется конвейер потока данных, который скачивает с веб-сайта книгу *"Илиада" Гомера* и выполняет по ее тексту поиск, сопоставляющий каждое слово с другими словами, содержащими первые символы этого слова в обратном порядке. Формирование конвейера потока данных в этом документе состоит из следующих шагов.  
  
1. Создание блоков потока данных, которые участвуют в конвейере.  
  
2. Подсоединение каждого блока потока данных к следующему блоку в конвейере. Каждый блок получает в качестве входных данных выходные данные предыдущего блока в конвейере.  
  
3. Для каждого блока потока данных создайте задачу продолжения, которая переводит следующий блок в завершенное состояние, после того как заканчивается выполнение предыдущего блока.  
  
4. Отправьте данные в начало конвейера.  
  
5. Пометьте начало конвейера как завершенное.  
  
6. Подождите, пока конвейер не завершит всю работу.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Прежде чем начать выполнение этого пошагового руководства, ознакомьтесь с документом [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
## <a name="creating-a-console-application"></a>Создание консольного приложения  
 В Visual Studio создайте проект "Консольное приложение" на Visual C# или Visual Basic. Установите пакет System.Threading.Tasks.Dataflow NuGet.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

 Добавьте следующий код в проект для создания простого приложения.  
  
 [!code-csharp[TPLDataflow_Palindromes#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#2)]
 [!code-vb[TPLDataflow_Palindromes#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromesemptymain.vb#2)]  
  
## <a name="creating-the-dataflow-blocks"></a>Создание блоков потоков данных  
 Добавьте следующий код в метод `Main` для создания блоков потока данных, которые участвуют в конвейере. Таблица ниже описывает роль каждой части конвейера.  
  
 [!code-csharp[TPLDataflow_Palindromes#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#3)]
 [!code-vb[TPLDataflow_Palindromes#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#3)]  
  
|Член|Тип|ОПИСАНИЕ|  
|------------|----------|-----------------|  
|`downloadString`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Загружает текст книги из Интернета.|  
|`createWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Разбивает текст книги на массив слов.|  
|`filterWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Удаляет из массива слов короткие слова и повторяющиеся значения.|  
|`findReversedWords`|<xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>|Находит все слова в отфильтрованной коллекции массива слов, которые также встречаются в массиве слов с обратным порядком символов.|  
|`printReversedWords`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Выводит на консоль слова и соответствующие обратные слова.|  
  
 Хотя можно объединить несколько шагов конвейера потока данных в этом примере в один шаг, на примере демонстрируется концепция создания нескольких независимых задач потока данных для выполнения более крупной задачи. В примере используется <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, чтобы позволить каждой части конвейера выполнить операцию с ее входными данными и отправить результат на следующий этап конвейера. Часть конвейера `findReversedWords` — это объект <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>, поскольку он создает несколько независимых выходных данных для каждого входного значения. Конец конвейера `printReversedWords` — это объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, так как он выполняет действие со входными данными и не создает выходных данных.  
  
## <a name="forming-the-pipeline"></a>Формирование конвейера  
 Добавьте следующий код, чтобы подсоединить каждый блок к следующему блоку конвейера.  
  
 При вызове метода <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> для подсоединения блока потока данных источника к блоку потока данных целевого объекта, блок потока данных источника передает данные блокам целевых объектов, как только данные становятся доступны. Если вы предоставите <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions>, у которого <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.PropagateCompletion> имеет значение true, успешное или неуспешное завершение одного блока в конвейере приведет к завершению следующего блока в конвейере.
  
 [!code-csharp[TPLDataflow_Palindromes#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#4)]
 [!code-vb[TPLDataflow_Palindromes#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#4)]  
  
## <a name="posting-data-to-the-pipeline"></a>Передача данных в конвейере  
 Добавьте следующий код, чтобы поместить url-адрес книги *"Илиада" Гомера* в начало конвейера потока данных.  
  
 [!code-csharp[TPLDataflow_Palindromes#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#6)]
 [!code-vb[TPLDataflow_Palindromes#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#6)]  
  
 В этом примере используется <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A?displayProperty=nameWithType> для синхронной отправки данных в начало конвейера. Используйте метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A?displayProperty=nameWithType> при необходимости асинхронной отправки данных в узел потока данных.  
  
## <a name="completing-pipeline-activity"></a>Завершение работы конвейера  
 Добавьте следующий код, чтобы пометить начало конвейера как завершенное. Начало конвейера отмечает свое выполнение, когда завершит обработку всех накопленных в буфере сообщений.
  
 [!code-csharp[TPLDataflow_Palindromes#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#7)]
 [!code-vb[TPLDataflow_Palindromes#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#7)]  
  
 Этот пример отправляет один url-адрес через конвейер потока данных для обработки. Если на вход подается более одного элемента данных, вызовите метод <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A?displayProperty=nameWithType> после передачи всех входных данных. Этот шаг можно пропустить, если в вашем приложении нет определенной точки, в которой данные более недоступны или приложение не должно ожидать завершения работы конвейера.  
  
## <a name="waiting-for-the-pipeline-to-finish"></a>Ожидание завершения работы конвейера  
 Добавьте следующий код, чтобы ожидать завершения работы конвейера. Операция в целом считается завершенной, когда завершит работу конец конвейера.  
  
 [!code-csharp[TPLDataflow_Palindromes#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#8)]
 [!code-vb[TPLDataflow_Palindromes#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#8)]  
  
 Можно ожидать завершения потока данных из любого потока или из нескольких потоков одновременно.  
  
## <a name="the-complete-example"></a>Полный пример  
 В следующем примере приведен полный код для этого руководства.  
  
 [!code-csharp[TPLDataflow_Palindromes#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#1)]
 [!code-vb[TPLDataflow_Palindromes#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#1)]  
  
## <a name="next-steps"></a>Следующие шаги  
 В этом примере один url-адрес отправляется на обработку через конвейер потока данных. Если через конвейер отправляется более одного входного значения, можно внедрить в приложении форму параллелизма, которая напоминает перемещение деталей по автомобильному заводу. Когда первая часть конвейера отправляет свой результат второй части, она может обрабатывать другой элемент параллельно с тем, как вторая часть обрабатывает первый результат.  
  
 Параллелизм, достигаемый за счет применения конвейеров потока данных, обозначается как *грубый параллелизм*, поскольку он включает небольшое количество крупных задач. Можно также использовать более *точный параллелизм*, включив в конвейер потока данных задачи меньшего размера, выполняющиеся быстрее. В этот пример конвейера включен элемент `findReversedWords`, который использует метод [PLINQ](parallel-linq-plinq.md) для параллельной обработки нескольких элементов в списке работ. Использование точного параллелизма в конвейере с несколькими крупными функциями может повысить общую пропускную способность.  
  
 Вы также можете подсоединить блок-источник потока данных к нескольким целевым блокам для создания *сети потока данных*. Перегруженная версия метода <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> принимает объект <xref:System.Predicate%601>, который определяет, примет ли целевой объект сообщение, основываясь на его значении. Большинство типов блоков потока данных, выполняющих роль источников, предлагают сообщения всем подключенным целевым блокам в порядке их подсоединения, пока один из блоков не примет это сообщение. С помощью этого механизма фильтрации можно создавать системы связанных блоков потока данных, которые будут направлять определенные по одному пути, а другие данные — по другому пути. Пример, использующий фильтрацию для создания сети потока данных, см. в статье [Пошаговое руководство. Использование потока данных в приложении Windows Forms](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)  
  
## <a name="see-also"></a>См. также

- [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
