---
title: "Applying Interop Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "design-time attributes"
  - ".NET Framework, exposing components to COM"
  - "attributes [.NET Framework], design-time functionality"
  - "conversion-tool attributes"
  - "attributes [.NET Framework], interop-specific"
  - "attributes [.NET Framework], conversion-tool"
  - "interoperation with unmanaged code, applying attributes"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "COM interop, exposing COM components"
  - "COM interop, applying attributes"
ms.assetid: b6014613-641c-4912-9e2f-83a99210a037
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Applying Interop Attributes
Пространство имен <xref:System.Runtime.InteropServices> предоставляет три категории атрибутов, связанных с взаимодействием: атрибуты, применяемые во время разработки, атрибуты, применяемые средствами COM\-взаимодействия и интерфейсами API в процессе преобразования, и атрибуты, применяемые разработчиком или COM\-взаимодействием.  
  
 Если разработчик незнаком с задачей применения атрибутов к управляемому коду, см. раздел [Расширение метаданных с помощью атрибутов](../../../docs/standard/attributes/index.md).  Как и другие настраиваемые атрибуты, атрибуты взаимодействия можно применять к типам, методам, свойствам, параметрам, полям и прочим членам.  
  
## Атрибуты времени разработки  
 Настроить результат процесса преобразования, выполняемого средствами COM\-взаимодействия и API\-интерфейсами, можно с помощью атрибутов времени разработки.  В следующей таблице описываются атрибуты, применимые к управляемому исходному коду.  При необходимости атрибуты, описанные в этой таблице, могут применяться также средствами COM\-взаимодействия.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|<xref:System.Runtime.InteropServices.AutomationProxyAttribute>|Определяет, следует ли маршалировать типа с помощью автоматического модуля или с помощью настраиваемого прокси\-сервера и заглушки.|  
|<xref:System.Runtime.InteropServices.ClassInterfaceAttribute>|Управляет типом интерфейса, создаваемого для класса.|  
|<xref:System.Runtime.InteropServices.CoClassAttribute>|Определяет значение CLSID исходного компонентного класса, импортируемого из библиотеки типов.<br /><br /> Этот атрибут обычно применяется средствами COM\-взаимодействия.|  
|<xref:System.Runtime.InteropServices.ComImportAttribute>|Указывает, что определение компонентного класса или интерфейса было импортировано из библиотеки COM\-типов.  Среда выполнения использует этот флаг, чтобы определить способ активации и маршалинга типа.  Этот атрибут запрещает экспорт типа обратно в библиотеку типов.<br /><br /> Этот атрибут обычно применяется средствами COM\-взаимодействия.|  
|<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>|Указывает, что при регистрации сборки для использования из COM должен вызываться метод. Это позволяет в процессе регистрации выполнять код, написанный разработчиком.|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|Задает интерфейсы, которые являются источниками событий для данного класса.<br /><br /> Этот атрибут также может применяться средствами COM\-взаимодействия.|  
|<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>|Указывает, что при отмене регистрации сборки для работы с COM должен вызываться метод. Это позволяет в процессе отмены регистрации выполнять код, написанный разработчиком.|  
|<xref:System.Runtime.InteropServices.ComVisibleAttribute>|Если значение атрибута равно **false**, отображает невидимые для COM типы.  Этот атрибут может применяться к отдельному типу или ко всей сборке, чтобы управлять видимостью для COM.  По умолчанию все управляемые открытые типы видимы. Чтобы сделать их видимыми, применять данный атрибут не требуется.|  
|<xref:System.Runtime.InteropServices.DispIdAttribute>|Задает идентификатор диспетчера COM \(DISPID\) для метода или поля.  Атрибут, содержащий идентификатор DISPID для описываемого метода, поля или свойства.<br /><br /> Этот атрибут также может применяться средствами COM\-взаимодействия.|  
|<xref:System.Runtime.InteropServices.FieldOffsetAttribute>|Задает физическое расположение каждого поля в пределах класса при использовании с **StructLayoutAttribute**, если для **LayoutKind** установлено значение Explicit.|  
|<xref:System.Runtime.InteropServices.GuidAttribute>|Задает глобальный идентификатор \(GUID\) класса, интерфейса или всей библиотеки типов.  Строка, передаваемая атрибуту, должна представлять собой формат, являющийся допустимым аргументом конструктора для типа **System.Guid**.<br /><br /> Этот атрибут также может применяться средствами COM\-взаимодействия.|  
|[IDispatchImpAttribute](frlrfsystemruntimeinteropservicesidispatchimplattributeclasstopic)|Указывает, какая из реализаций интерфейса **IDispatch** используется средой CLR при предоставлении COM сдвоенных интерфейсов и диспетчерских интерфейсов.|  
|<xref:System.Runtime.InteropServices.InAttribute>|Указывает, что должен быть выполнен маршалинг данных в вызывающий объект.  Может использоваться, чтобы задать атрибуты для параметров.|  
|<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>|Указывает, как управляемый интерфейс предоставляется COM\-клиентам \(сдвоенный, производный от IUnknown или только IDispatch\).<br /><br /> Этот атрибут также может применяться средствами COM\-взаимодействия.|  
|<xref:System.Runtime.InteropServices.LCIDConversionAttribute>|Указывает, что для неуправляемой сигнатуры метода требуется параметр LCID.<br /><br /> Этот атрибут также может применяться средствами COM\-взаимодействия.|  
|<xref:System.Runtime.InteropServices.MarshalAsAttribute>|Указывает, как должен быть организован маршалинг параметров или данных в полях между управляемым и неуправляемым программным кодом.  Этот атрибут всегда необязателен, так как для каждого типа данных существует режим маршалинга по умолчанию.<br /><br /> Этот атрибут также может применяться средствами COM\-взаимодействия.|  
|<xref:System.Runtime.InteropServices.OptionalAttribute>|Указывает, что данный параметр необязателен.<br /><br /> Этот атрибут также может применяться средствами COM\-взаимодействия.|  
|<xref:System.Runtime.InteropServices.OutAttribute>|Указывает, что должен быть выполнен маршалинг параметров или данных полей из вызываемого объекта обратно в вызывающий.|  
|<xref:System.Runtime.InteropServices.PreserveSigAttribute>|Подавляет преобразование определенного в сигнатуре возвращаемого значения HRESULT или retval, обычно происходящее при вызовах взаимодействия.  Этот атрибут влияет на маршалинг и экспорт библиотек типов.<br /><br /> Этот атрибут также может применяться средствами COM\-взаимодействия.|  
|<xref:System.Runtime.InteropServices.ProgIdAttribute>|Задает идентификатор ProgID класса .NET Framework.  Может использоваться в качестве атрибута классов.|  
|<xref:System.Runtime.InteropServices.StructLayoutAttribute>|Управляет физической компоновкой полей класса.<br /><br /> Этот атрибут также может применяться средствами COM\-взаимодействия.|  
  
## Атрибуты средств преобразования  
 В следующей таблице описываются атрибуты, применяемые средствами COM\-взаимодействия в ходе преобразования.  Во время разработки эти атрибуты не применяются.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|<xref:System.Runtime.InteropServices.ComAliasNameAttribute>|Показывает COM\-псевдонимы для типа параметра или поля.  Может использоваться в качестве атрибута параметров, полей или возвращаемых значений.|  
|<xref:System.Runtime.InteropServices.ComConversionLossAttribute>|Указывает, что сведения о классе или интерфейсе были утеряны при импорте из библиотеки типов в сборку.|  
|<xref:System.Runtime.InteropServices.ComEventInterfaceAttribute>|Определяет исходный интерфейс и класс, реализующий методы интерфейса события.|  
|<xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>|Показывает, что сборка была первоначально импортирована из библиотеки COM\-типов.  Этот атрибут содержит определение исходной библиотеки типов.|  
|<xref:System.Runtime.InteropServices.TypeLibFuncAttribute>|Содержит флаги **FUNCFLAGS**, которые были первоначально импортированы для данной функции из библиотеки COM\-типов.|  
|<xref:System.Runtime.InteropServices.TypeLibTypeAttribute>|Содержит флаги **TYPEFLAGS**, ранее импортированные для данного типа из библиотеки COM\-типов.|  
|<xref:System.Runtime.InteropServices.TypeLibVarAttribute>|Содержит флаги **VARFLAGS**, которые были первоначально импортированы для данной переменной из библиотеки COM\-типов.|  
  
## См. также  
 <xref:System.Runtime.InteropServices>   
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Атрибуты](../../../docs/standard/attributes/index.md)   
 [Qualifying .NET Types for Interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [Packaging an Assembly for COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)