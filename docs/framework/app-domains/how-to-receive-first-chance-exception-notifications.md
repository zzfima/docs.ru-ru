---
title: "Практическое руководство. Получение уведомлений о первом этапе обработки исключений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "исключения, уведомления о первом этапе"
  - "уведомления о первом этапе обработки исключений"
ms.assetid: 66f002b8-a97d-4a6e-a503-2cec01689113
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Получение уведомлений о первом этапе обработки исключений
Событие <xref:System.AppDomain.FirstChanceException> класса <xref:System.AppDomain> позволяет получать уведомления о порождении исключений до того, как среда CLR начнет искать обработчики исключений.  
  
 Событие порождается на уровне домена приложения.  Поток выполнения может проходить несколько доменов приложения, поэтому необработанное в одном домене исключения может быть обработано в другом домене.  Уведомление происходит во всех доменах приложения, добавивших обработчик для этого события, пока исключение не будет обработано.  
  
 Процедуры и примеры в этой статье демонстрируют, как можно получать уведомления о первичных исключениях в рамках простой программы с одним доменом приложения, а также в созданном пользователем домене приложения.  
  
 Более развернутый пример с несколькими доменами приложения см. в описании события <xref:System.AppDomain.FirstChanceException>.  
  
## Получение уведомлений о первичном исключении в домене приложения по умолчанию  
 В представленной ниже процедуре точка входа для приложения, метод `Main()`, запускается в домене приложения по умолчанию.  
  
#### Демонстрация уведомлений о первичном исключении в домене приложения по умолчанию  
  
1.  Определите обработчик событий для события <xref:System.AppDomain.FirstChanceException>, используя лямбда\-функцию, и присоедините его к событию.  В этом примере обработчик событий выводит имя домена приложения, где событие было обработано, а также свойство исключения <xref:System.Exception.Message%2A>.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#2)]  
  
2.  Породите исключение и перехватите его.  Еще до того, как среда выполнения найдет обработчик исключений, будет вызвано событие <xref:System.AppDomain.FirstChanceException>, которое отобразит сообщение.  За ним последует это сообщение, которое отображается обработчиком исключений.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#3)]  
  
3.  Вызовите исключение, но не перехватывайте его.  Еще до того, как среда выполнения начнет искать обработчик исключений, будет вызвано событие <xref:System.AppDomain.FirstChanceException>, которое отобразит сообщение.  Обработчика исключений нет, поэтому приложение завершит работу.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#4)]  
  
     Приведенный ниже \(в первых трех шагах этой процедуры\) код формирует полное консольное приложение.  Выходные данные приложения зависят от имени EXE\-файла, потому что имя домена приложения по умолчанию состоит из имени и расширения EXE\-файла.  В следующем примере показаны выходные данные.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#5)]  
  
## Получение уведомлений о первичном исключении в другом домене приложения  
 Если в программе имеется несколько доменов приложения, можно выбирать, какие из них должны получать уведомления.  
  
#### Получение уведомлений о первичном исключении в созданном пользователем домене приложения  
  
1.  Определите обработчик событий <xref:System.AppDomain.FirstChanceException>.  В примере используется метод `static` \(`Shared` в Visual Basic\), выводящий имя домена приложения, обработавшего исключение, и свойство <xref:System.Exception.Message%2A> исключения.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#3)]  
  
2.  Создайте домен приложения и добавьте обработчик событий <xref:System.AppDomain.FirstChanceException> для этого домена приложения.  В этом примере домен приложения называется `AD1`.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#2)]  
  
     Данное событие можно аналогичным образом обработать в домене приложения по умолчанию.  Используйте свойство <xref:System.AppDomain.CurrentDomain%2A?displayProperty=fullName> с модификатором `static` \(`Shared` в Visual Basic\) в методе `Main()`, чтобы получить ссылку на домен приложения по умолчанию.  
  
#### Демонстрация уведомлений о первичном исключении в домене приложения  
  
1.  Создайте объект `Worker` в домене приложения, созданном в предыдущей процедуре.  Класс `Worker` должен быть открытым наследником <xref:System.MarshalByRefObject>, как показано в полном примере в конце статьи.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#4)]  
  
2.  Вызовите метод объекта `Worker`, порождающий исключение.  В этом примере метод `Thrower` вызывается дважды.  В первый раз аргумент метода равен `true`, в результате чего метод перехватывает собственное исключение самостоятельно.  Во второй раз аргумент равен `false`, и метод `Main()` перехватывает исключение в домене приложения по умолчанию.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#6)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#6)]  
  
3.  Поместите в метод `Thrower` код, отвечающий за то, будет ли метод обрабатывать собственное исключение.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#5)]  
  
## Пример  
 В следующем примере создается домен приложения `AD1`, после чего для события <xref:System.AppDomain.FirstChanceException> этого домена добавляется обработчик событий.  Затем в этом домене приложения создается экземпляр класса `Worker` и вызывается метод `Thrower`, порождающий исключение <xref:System.ArgumentException>.  В зависимости от значения аргумента метод либо перехватит исключение, либо не сможет его обработать.  
  
 При каждом порождении исключения методом `Thrower` в домене `AD1` в нем порождается событие <xref:System.AppDomain.FirstChanceException>, после чего обработчик событий отображает сообщение.  Затем среда выполнения ищет обработчик исключений.  В первом случае он обнаруживается в `AD1`.  Во втором случае исключение в `AD1` не обрабатывается и перехватывается только в домене приложения по умолчанию.  
  
> [!NOTE]
>  Имя домена приложения по умолчанию совпадает с именем исполняемого файла.  
  
 При добавлении обработчика для события <xref:System.AppDomain.FirstChanceException> в домене приложения по умолчанию событие порождается и обрабатывается еще до того, как домен приложения по умолчанию обработает исключение.  Чтобы увидеть, как это происходит, добавьте код на C\# `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;` \(в Visual Basic — `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceExceptio`n\) в начало метода `Main()`.  
  
 [!code-csharp[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#1)]
 [!code-vb[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#1)]  
  
## Компиляция кода  
  
-   Этот пример представляет собой приложение командной строки.  Для компиляции и запуска этого кода в [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] добавьте код на C\# `Console.ReadLine();` \(в Visual Basic — `Console.ReadLine()`\) в конец метода `Main()`, чтобы предотвратить закрытие командного окна до того, как вы успеете прочитать выходные данные.  
  
## См. также  
 <xref:System.AppDomain.FirstChanceException>