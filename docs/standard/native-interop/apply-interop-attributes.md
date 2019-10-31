---
title: Применение атрибутов взаимодействия
ms.date: 03/30/2017
helpviewer_keywords:
- design-time attributes
- .NET Framework, exposing components to COM
- attributes [.NET Framework], design-time functionality
- conversion-tool attributes
- attributes [.NET Framework], interop-specific
- attributes [.NET Framework], conversion-tool
- interoperation with unmanaged code, applying attributes
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
- COM interop, applying attributes
ms.assetid: b6014613-641c-4912-9e2f-83a99210a037
ms.openlocfilehash: 78f89c3c8784467d3ec396106de7bbb34a2022f6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121950"
---
# <a name="applying-interop-attributes"></a>Применение атрибутов взаимодействия
В пространстве имен <xref:System.Runtime.InteropServices> представлены три категории атрибутов взаимодействия: атрибуты, применяемые разработчиком во время разработки, API и средствами COM-взаимодействия в процессе преобразования, а также разработчиком или средой COM-взаимодействия.  
  
 Дополнительные сведения о применении атрибутов к управляемому коду см. в разделе [Расширение метаданных с помощью атрибутов](../../../docs/standard/attributes/index.md). Как и другие настраиваемые атрибуты, атрибуты взаимодействия можно применять к типам, методам, свойствам, параметрам, полям и другим членам.  
  
## <a name="design-time-attributes"></a>Атрибуты времени разработки  
 Атрибуты времени разработки позволяют настраивать результаты процесса преобразования, который выполняется API и средствами COM-взаимодействия. В следующей таблице описываются атрибуты, которые можно применять к управляемому исходному коду. В некоторых случаях средства COM-взаимодействия также могут применять описываемые здесь атрибуты.  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|<xref:System.Runtime.InteropServices.AutomationProxyAttribute>|Указывает, будет ли выполняться маршалинг типа с использованием маршалера автоматизации или настраиваемого прокси-сервера и заглушки.|  
|<xref:System.Runtime.InteropServices.ClassInterfaceAttribute>|Определяет тип интерфейса, создаваемого для класса.|  
|<xref:System.Runtime.InteropServices.CoClassAttribute>|Указывает идентификатор CLSID исходного компонентного класса, импортированного из библиотеки типов.<br /><br /> Этот атрибут обычно применяется средствами COM-взаимодействия.|  
|<xref:System.Runtime.InteropServices.ComImportAttribute>|Указывает, что определение компонентного класса или интерфейса было импортировано из библиотеки типов COM. Этот флаг используется средой выполнения, чтобы определить способ активации и маршалинга типа. Этот атрибут запрещает экспорт обратно в библиотеку типов.<br /><br /> Этот атрибут обычно применяется средствами COM-взаимодействия.|  
|<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>|Указывает, что метод должен вызываться при регистрации сборки для использования из модели COM, что позволяет выполнять написанный пользователем код в процессе регистрации.|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|Определяет интерфейсы, являющиеся источниками событий для класса.<br /><br /> Этот атрибут может применяться средствами COM-взаимодействия.|  
|<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>|Указывает, что метод должен вызываться при отмене регистрации сборки для использования из модели COM, что позволяет выполнять написанный пользователем код в ходе этого процесса.|  
|<xref:System.Runtime.InteropServices.ComVisibleAttribute>|Если значение атрибута равно **false**, отображает типы, невидимые для модели COM. Этот атрибут может применяться к отдельному типу или ко всей сборке для управления видимостью COM. По умолчанию все управляемые открытые типы являются видимыми, и использовать этот атрибут не нужно.|  
|<xref:System.Runtime.InteropServices.DispIdAttribute>|Указывает идентификатор диспетчера COM (DISPID) для метода или поля. Этот атрибут содержит идентификатор DISPID для метода, поля или свойства, которые он описывает.<br /><br /> Этот атрибут может применяться средствами COM-взаимодействия.| 
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute>|Указывает интерфейс по умолчанию для COM-класса, реализованного в .NET.<br /><br /> Этот атрибут может применяться средствами COM-взаимодействия.|
|<xref:System.Runtime.InteropServices.FieldOffsetAttribute>|Указывает физическое расположение каждого поля в классе при использовании с атрибутом **StructLayoutAttribute**, если атрибуту **LayoutKind** присвоено значение Explicit.|  
|<xref:System.Runtime.InteropServices.GuidAttribute>|Указывает глобальный уникальный идентификатор (GUID) класса, интерфейса или всей библиотеки типов. Строка, передаваемая атрибуту, должна иметь формат допустимого аргумента конструктора для типа **System.Guid**.<br /><br /> Этот атрибут может применяться средствами COM-взаимодействия.|  
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute>|Указывает, какую реализацию интерфейса **IDispatch** общеязыковая среда выполнения использует при предоставлении dual- и disp-интерфейсов для модели COM.|  
|<xref:System.Runtime.InteropServices.InAttribute>|Указывает, что данные необходимо маршалировать в вызывающий объект. Может использоваться в качестве атрибута параметров.|  
|<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>|Определяет, как управляемый интерфейс предоставляется клиентам COM (dual, производный от IUnknown или только IDispatch).<br /><br /> Этот атрибут может применяться средствами COM-взаимодействия.|  
|<xref:System.Runtime.InteropServices.LCIDConversionAttribute>|Указывает, что в сигнатуре неуправляемого метода требуется параметр кода языка (LCID).<br /><br /> Этот атрибут может применяться средствами COM-взаимодействия.|  
|<xref:System.Runtime.InteropServices.MarshalAsAttribute>|Указывает способ маршалинга данных полей или параметров между управляемым и неуправляемым кодом. Этот атрибут всегда является необязательным, поскольку для каждого типа данных определено поведение маршалинга по умолчанию.<br /><br /> Этот атрибут может применяться средствами COM-взаимодействия.|  
|<xref:System.Runtime.InteropServices.OptionalAttribute>|Указывает, что параметр является необязательным.<br /><br /> Этот атрибут может применяться средствами COM-взаимодействия.|  
|<xref:System.Runtime.InteropServices.OutAttribute>|Указывает, что данные поля или параметра должны маршалироваться из вызываемого объекта обратно в вызывающий.|  
|<xref:System.Runtime.InteropServices.PreserveSigAttribute>|Подавляет преобразование значения HRESULT или сигнатуры retval, которое обычно выполняется во время вызовов взаимодействия. Этот атрибут влияет на маршалинг и экспорт библиотеки типов.<br /><br /> Этот атрибут может применяться средствами COM-взаимодействия.|  
|<xref:System.Runtime.InteropServices.ProgIdAttribute>|Указывает идентификатор ProgID для класса .NET Framework. Может использоваться в качестве атрибута классов.|  
|<xref:System.Runtime.InteropServices.StructLayoutAttribute>|Управляет физической компоновкой полей класса.<br /><br /> Этот атрибут может применяться средствами COM-взаимодействия.|  
  
## <a name="conversion-tool-attributes"></a>Атрибуты средств преобразования  
 В следующей таблице описываются атрибуты, которые применяются средствами COM-взаимодействия во время преобразования. Эти атрибуты не применяются во время разработки.  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|<xref:System.Runtime.InteropServices.ComAliasNameAttribute>|Указывает псевдоним COM для типа параметра или поля. Может использоваться в качестве атрибута параметров, полей или возвращаемых значений.|  
|<xref:System.Runtime.InteropServices.ComConversionLossAttribute>|Указывает, что сведения о классе или интерфейсе были потеряны при импорте из библиотеки типов в сборку.|  
|<xref:System.Runtime.InteropServices.ComEventInterfaceAttribute>|Определяет исходный интерфейс и класс, реализующие методы интерфейса событий.|  
|<xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>|Указывает, что сборка была первоначально импортирована из библиотеки типов COM. Этот атрибут содержит определение исходной библиотеки типов.|  
|<xref:System.Runtime.InteropServices.TypeLibFuncAttribute>|Содержит флаги **FUNCFLAGS**, которые были первоначально импортированы для этой функции из библиотеки типов COM.|  
|<xref:System.Runtime.InteropServices.TypeLibTypeAttribute>|Содержит флаги **TYPEFLAGS**, которые были первоначально импортированы для этого типа из библиотеки типов COM.|  
|<xref:System.Runtime.InteropServices.TypeLibVarAttribute>|Содержит флаги **VARFLAGS**, которые были первоначально импортированы для этой переменной из библиотеки типов COM.|  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices>
- [Предоставление компонентов .NET Framework клиентам COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)
- [Атрибуты](../../../docs/standard/attributes/index.md)
- [Oпределение типов .NET для взаимодействия](../../../docs/standard/native-interop/qualify-net-types-for-interoperation.md)
- [Упаковка сборки .NET Framework для COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)
