---
title: "Общие сведения о библиотеке классов .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], library overview
- class objects value type
- naming conventions [.NET Framework]
- types, .NET Framework
- user-defined types
- Visual Basic, data types
- data types [.NET Framework], C++
- Visual C#, data types
- libraries, .NET Framework class library
- data types [.NET Framework], JScript
- System namespace
- JScript, data types
- .NET Framework, class library
- type system [.NET Framework]
- data types [.NET Framework]
- value types
- data types [.NET Framework], Visual Basic
- Common Language Specification
- namespaces [.NET Framework]
- floating point value type
- class library [.NET Framework]
- CLS
- logical value type
- .NET Framework class library, about
- built-in types
- namespaces [.NET Framework], about namespaces
- Visual C++, data types
- members [.NET Framework], type
- data types [.NET Framework], C#
- integer value type
- base types, class library
ms.assetid: 7e4c5921-955d-4b06-8709-101873acf157
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 607ef0020e15581c6ccca8f232eaea6be547f63b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="net-framework-class-library-overview"></a>Общие сведения о библиотеке классов .NET Framework
[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] содержит классы, интерфейсы и типы значений, которые облегчают и оптимизируют процесс разработки, а также обеспечивают доступ к функциям системы. Для упрощения взаимодействия между языками большинство типов платформы .NET Framework являются CLS-совместимыми, и поэтому их можно использовать в любом языке программирования, компилятор которого соответствует спецификации CLS.  
  
 Типы .NET Framework представляют собой основу для создания элементов управления, компонентов и приложений .NET. [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] содержит типы, предназначенные для следующих задач:  
  
-   представление базовых типов данных и исключений;  
  
-   инкапсуляция структур данных;  
  
-   операции ввода-вывода;  
  
-   доступ к данным о загруженных типах;  
  
-   вызов проверок безопасности .NET Framework;  
  
-   доступ к данным, предоставление графического пользовательского интерфейса на стороне клиента и управляемого сервером графического пользовательского интерфейса на стороне клиента.  
  
 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] предлагает расширенный набор интерфейсов, а также абстрактных и конкретных (неабстрактных) классов. Можно использовать существующие конкретные классы, кроме того, во многих случаях на их основе можно создавать собственные производные классы. Чтобы использовать возможности интерфейса, можно либо создать класс, реализующий интерфейс, либо создать производный класс на основе одного из классов .NET Framework, реализующего интерфейс.  
  
## <a name="naming-conventions"></a>Соглашения об именах  
 Для типов платформы .NET Framework используется схема именования через точку, описывающая иерархию. При таком подходе связанные типы группируются в пространства имен, что упрощает их поиск и создание ссылок. Первая часть полного имени — до крайней правой точки — это имя пространства имен. Последняя часть имени — это имя типа. Например **System.Collections.ArrayList** представляет собой тип **ArrayList**, который принадлежит пространству имен **System.Collections**. Типы в **System.Collections** можно использовать для работы с коллекциями объектов.  
  
 Такая схема именования упрощает разработчикам библиотек задачу расширения [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] с целью создания иерархических групп типов и присвоения им согласованных между собой и понятных имен. Она также позволяет однозначно идентифицировать типы по их полным именам (то есть по пространству имен и имени типа), что предотвращает конфликты имен типов. Ожидается, при именовании пространств имен разработчики библиотек будут руководствоваться следующим соглашением:  
  
 *CompanyName*.*TechnologyName*  
  
 Например, пространство имен Microsoft.Word соответствует этому правилу.  
  
 Использование шаблонов именования для группировки связанных типов в пространства имен очень полезно при создании и документировании библиотек классов. Однако такая схема именования не влияет на видимость, доступ к членам, наследование, безопасность и привязки. Пространство имен может быть разделено между несколькими сборками, и одна сборка может содержать типы из нескольких пространств имен. Сборка представляет собой формальную структуру для управления версиями, развертывания, обеспечения безопасности, загрузки и обеспечения видимости в среде CLR.  
  
 Дополнительные сведения о пространствах имен и именах типов см. в разделе [Система общих типов CTS](../../docs/standard/base-types/common-type-system.md).  
  
## <a name="system-namespace"></a>Пространство имен System  
 Пространство имен <xref:System> является корневым пространством имен для основных типов в [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]. Это пространство имен включает классы, представляющие собой базовые типы данных, используемые всеми приложениями: <xref:System.Object> (корень иерархии наследования), <xref:System.Byte>, <xref:System.Char>, <xref:System.Array>, <xref:System.Int32>, <xref:System.String> и т. д. Многие из этих типов соответствуют простым типам данных, которые используются в языке программирования. При написании кода с применением типов .NET Framework можно использовать соответствующее ключевое слово языка для базового типа данных .NET Framework.  
  
 В следующей таблице перечислены базовые типы, предоставляемые в [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], кратко описывается каждый тип и указывается соответствующий тип в Visual Basic, C#, C++ и JScript.  
  
|Категория|Имя класса|Описание:|Тип данных в Visual Basic|Тип данных в C#|Тип данных в C++|Тип данных в JScript|  
|--------------|----------------|-----------------|----------------------------|-------------------|---------------------|-----------------------|  
|Целое число|<xref:System.Byte>|8-разрядное целое число без знака.|**Byte**|**byte**|**unsigned char**|**Byte**|  
||<xref:System.SByte>|8-битовое целое число со знаком.<br /><br /> Не является CLS-совместимым.|**SByte**|**sbyte**|**char**<br /><br /> - или -<br /><br /> **signed** **char**|**SByte**|  
||<xref:System.Int16>|16-разрядное знаковое целое число.|**Short**|**short**|**short**|**short**|  
||<xref:System.Int32>|32-разрядное знаковое целое число.|**Integer**|**int**|**int**<br /><br /> - или -<br /><br /> **long**|**int**|  
||<xref:System.Int64>|64-разрядное целое число со знаком.|**Long**|**long**|**__int64**|**long**|  
||<xref:System.UInt16>|16-разрядное целое число без знака.<br /><br /> Не является CLS-совместимым.|**UShort**|**ushort**|**unsigned short**|**UInt16**|  
||<xref:System.UInt32>|32-разрядное целое число без знака.<br /><br /> Не является CLS-совместимым.|**UInteger**|**uint**|**unsigned int**<br /><br /> - или -<br /><br /> **unsigned long**|**UInt32**|  
||<xref:System.UInt64>|64-разрядное целое число без знака.<br /><br /> Не является CLS-совместимым.|**ULong**|**ulong**|**unsigned __int64**|**UInt64**|  
|С плавающей запятой|<xref:System.Single>|Число с плавающей запятой с обычной точностью (32-разрядное).|**Single**|**float**|**float**|**float**|  
||<xref:System.Double>|Число с плавающей запятой с двойной точностью (64-разрядное).|**Double**|**double**|**double**|**double**|  
|Logical|<xref:System.Boolean>|Логическое значение (true или false).|**Boolean**|**bool**|**bool**|**bool**|  
|Другое|<xref:System.Char>|Символ Юникода (16-разрядный).|**Char**|**char**|**wchar_t**|**char**|  
||<xref:System.Decimal>|128-разрядное десятичное значение.|**Decimal**|**decimal**|**Decimal**|**Decimal**|  
||<xref:System.IntPtr>|Целое число со знаком, размер которого зависит от базовой платформы (32-разрядное значение при 32-разрядной платформе и 64-разрядное значение при 64-разрядной платформе).|**IntPtr**<br /><br /> Не является встроенным типом.|**IntPtr**<br /><br /> Не является встроенным типом.|**IntPtr**<br /><br /> Не является встроенным типом.|**IntPtr**|  
||<xref:System.UIntPtr>|Целое число без знака, размер которого зависит от базовой платформы (32-разрядное значение при 32-разрядной платформе и 64-разрядное значение при 64-разрядной платформе).<br /><br /> Не является CLS-совместимым.|**UIntPtr**<br /><br /> Не является встроенным типом.|**UIntPtr**<br /><br /> Не является встроенным типом.|**UIntPtr**<br /><br /> Не является встроенным типом.|**UIntPtr**|  
объекты ass|<xref:System.Object>|Корень иерархии объектов.|**Объект**|**object**|**Object\***|**Объект**|  
||<xref:System.String>|Неизменяемая строка символов Юникода фиксированной длины.|**String**|**string**|**String\***|**String**|  
  
 В дополнение к базовым типам данных пространство имен <xref:System> содержит более 100 классов — от классов для обработки исключений до классов, которые работают с основными механизмами среды выполнения, такими как домены приложений и сборщик мусора. Пространство имен <xref:System> также содержит много пространств имен второго уровня.  
  
 Дополнительные сведения о пространствах имен см. в [Библиотеке классов .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195). В справочной документации представлен краткий обзор каждого пространства имен, а также дано формальное описание каждого типа и его членов.  
  
## <a name="see-also"></a>См. также  
 [Система общих типов CTS](../../docs/standard/base-types/common-type-system.md)  
 [Библиотека классов .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195)  
 [Обзор набора средств Visual Studio для Unity](../../docs/framework/get-started/overview.md)
