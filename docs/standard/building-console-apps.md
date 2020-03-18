---
title: Построение консольных приложений в .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework, building console applications
- application development [.NET Framework], console
- console applications
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
ms.openlocfilehash: 1ec65795a7f3d706b2878dd8a8397ae42b61ce7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73132864"
---
# <a name="building-console-applications-in-the-net-framework"></a>Построение консольных приложений в .NET Framework
Приложения .NET Framework могут использовать класс <xref:System.Console?displayProperty=nameWithType> для выполнения консольного ввода-вывода символов. Данные, поступающие от консоли, считываются из стандартного потока ввода, выводимые на консоль данные записываются в стандартный поток вывода, а сведения об ошибках записываются в стандартный поток вывода ошибок. Эти потоки автоматически связываются с консолью при запуске приложения и представлены свойствами <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> и <xref:System.Console.Error%2A> соответственно.  
  
 Значением свойства <xref:System.Console.In%2A?displayProperty=nameWithType> является объект <xref:System.IO.TextReader?displayProperty=nameWithType>, а значениями свойств <xref:System.Console.Out%2A?displayProperty=nameWithType> и <xref:System.Console.Error%2A?displayProperty=nameWithType> — объекты <xref:System.IO.TextWriter?displayProperty=nameWithType>. Эти свойства можно связывать с потоками, не представляющими консоль, что позволяет задать для любого из потоков другой источник или приемник данных. Например, можно перенаправить вывод в файл, присвоив свойству <xref:System.Console.Out%2A?displayProperty=nameWithType> объект <xref:System.IO.StreamWriter?displayProperty=nameWithType>, инкапсулирующий <xref:System.IO.FileStream?displayProperty=nameWithType> с помощью метода <xref:System.Console.SetOut%2A?displayProperty=nameWithType>. Свойства <xref:System.Console.In%2A?displayProperty=nameWithType> и <xref:System.Console.Out%2A?displayProperty=nameWithType> не обязательно должны быть связаны с одним потоком.  
  
> [!NOTE]
> Дополнительные сведения о построении консольных приложений, включая образцы в C#, Visual Basic, и C++, см. в документации к классу <xref:System.Console>.  
  
 При отсутствии консоли, например в Windows-приложениях, выводимые в стандартный поток вывода данные не отображаются для пользователя, так как их некуда выводить. Запись информации в недоступную консоль не приводит к возникновению исключения.  
  
 Кроме того, чтобы использовать консоль для чтения и записи в приложении на базе Windows, разработанном в Visual Studio, откройте диалоговое окно **Свойства** проекта, перейдите на вкладку **Приложение** и задайте для параметра **Тип приложения** значение **Консольное приложение**.  
  
 У консольных приложений отсутствует запускаемый по умолчанию механизм сообщений. Поэтому вызовы таймеров Microsoft Win32 из такого приложения могут завершаться неудачей.  
  
 У класса **System.Console** имеются методы, позволяющие считывать с консоли отдельные символы или целые строки. Другие методы выполняют преобразование данных и форматирование строковых значений, а затем выводят отформатированные строки на консоль. Дополнительные сведения о форматировании строк см. в статье [Общие сведения о форматировании](../../docs/standard/base-types/formatting-types.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Console?displayProperty=nameWithType>
- [Типы форматирования](../../docs/standard/base-types/formatting-types.md)
