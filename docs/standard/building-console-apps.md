---
title: "Построение консольных приложений в .NET Framework | Microsoft Docs"
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
  - "платформа .NET Framework, построение консольных приложений"
  - "разработка приложений [платформа .NET Framework], консоль"
  - "консольные приложения"
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Построение консольных приложений в .NET Framework
Приложения .NET Framework могут использовать класс <xref:System.Console?displayProperty=fullName> для выполнения консольного ввода\-вывода символов.  Данные, поступающие от консоли, считываются из стандартного потока ввода, выводимые на консоль данные записываются в стандартный поток вывода, а сведения об ошибках записываются в стандартный поток вывода ошибок.  Эти потоки автоматически связываются с консолью при запуске приложения и представлены свойствами <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> и <xref:System.Console.Error%2A> соответственно.  
  
 Значением свойства <xref:System.Console.In%2A?displayProperty=fullName> является объект <xref:System.IO.TextReader?displayProperty=fullName>, а значениями свойств <xref:System.Console.Out%2A?displayProperty=fullName> и <xref:System.Console.Error%2A?displayProperty=fullName> — объекты <xref:System.IO.TextWriter?displayProperty=fullName>.  Эти свойства можно связывать с потоками, не представляющими консоль, что позволяет задать для любого из потоков другой источник или приемник данных.  Например, можно перенаправить вывод в файл, присвоив свойству <xref:System.Console.Out%2A?displayProperty=fullName> объект <xref:System.IO.StreamWriter?displayProperty=fullName>, инкапсулирующий <xref:System.IO.FileStream?displayProperty=fullName> с помощью метода <xref:System.Console.SetOut%2A?displayProperty=fullName>.  Свойства <xref:System.Console.In%2A?displayProperty=fullName> и <xref:System.Console.Out%2A?displayProperty=fullName> не обязательно должны быть связаны с одним потоком.  
  
> [!NOTE]
>  Дополнительные сведения о построении консольных приложений, включая образцы в C\#, Visual Basic, и C\+\+, см. в документации к классу <xref:System.Console>.  
  
 При отсутствии консоли, например в Windows\-приложениях, выводимые в стандартный поток вывода данные не отображаются для пользователя, так как их некуда выводить.  Запись информации в недоступную консоль не приводит к возникновению исключения.  
  
 Чтобы использовать консоль для чтения и записи в Windows\-приложении, разработанном в Visual Studio, откройте диалоговое окно **Свойства** проекта, перейдите на вкладку **Приложение** и задайте для параметра **Тип приложения** значение **Консольное приложение**.  
  
 У консольных приложений отсутствует запускаемый по умолчанию механизм сообщений.  Поэтому вызовы таймеров Microsoft Win32 из такого приложения могут завершаться неудачей.  
  
 У класса **System.Console** имеются методы, позволяющие считывать с консоли отдельные символы или целые строки.  Другие методы выполняют преобразование данных и форматирование строковых значений, а затем выводят отформатированные строки на консоль.  Дополнительные сведения о форматировании строк см. в разделе [Типы форматирования](../../docs/standard/base-types/formatting-types.md).  
  
## См. также  
 <xref:System.Console?displayProperty=fullName>   
 [Типы форматирования](../../docs/standard/base-types/formatting-types.md)