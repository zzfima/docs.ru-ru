---
title: "Метод ICorDebugProcess6::EnableVirtualModuleSplitting"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d6e1f459636f1bb2b3844eebdb98bebd1deb73cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a>Метод ICorDebugProcess6::EnableVirtualModuleSplitting
Позволяет включить или отключить разделение виртуальных модулей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `enableSplitting`  
 `true`, чтобы включить разделение виртуальных модулей; `false`, чтобы отключить его.  
  
## <a name="remarks"></a>Примечания  
 Разделении виртуальных модулей [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) распознает модули, которые были объединены во время построения и представляет их в виде группы отдельных модулей, а не одного крупного модуля. При этом изменяется поведение различных [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) описанных ниже методов.  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
 Этот метод может быть вызван, и значение `enableSplitting` может быть изменено, в любое время. Не вызывает никакие с отслеживанием состояния функциональные изменения в [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) объекта, но только меняет поведение методов, перечисленных в [разделение виртуальных модулей и неуправляемые интерфейсы API отладки](#APIs) раздел в момент их вызова. Применение виртуальных модулей приводит к ухудшению производительности при вызове этих методов. Кроме того, значительное кэширование в памяти виртуализованных метаданных может потребоваться для правильной реализации [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) API-интерфейсы и эти кэши могут сохраняться даже после разделения виртуальных модулей было отключено.  
  
## <a name="terminology"></a>Терминология  
 При описании разделения виртуальных модулей используются следующие термины:  
  
 контейнерные модули или контейнеры  
 Агрегатные модули.  
  
 вложенные модули или виртуальные модули  
 Модули, находящиеся в контейнере.  
  
 обычные модули  
 Модули, которые не были объединены во время построения. Они не являются ни вложенными, ни контейнерными модулями.  
  
 Контейнерные модули и вложенные модули представляются объектами интерфейса ICorDebugModule. Однако поведение интерфейса несколько отличается в каждом случае как \<x-ref раздел > описывает раздел.  
  
## <a name="modules-and-assemblies"></a>Модули и сборки  
 Сборки с несколькими модулями не поддерживаются для сценариев объединения сборок, поэтому существует однозначное соответствие между модулем и сборкой. Каждый объект ICorDebugModule, независимо от того, представляет он контейнерный или вложенный модуль, имеет соответствующий объект ICorDebugAssembly. [ICorDebugModule::GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) будут преобразованы из модуля в сборку. Для сопоставления в противоположном направлении [ICorDebugAssembly::EnumerateModules](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md) метод перечисляет только один модуль. Так как сборка и модуль образуют в данном случае тесно связанную пару, термины «сборка и модуль» становятся в значительной степени взаимозаменяемыми.  
  
## <a name="behavioral-differences"></a>Различия в поведении  
 Контейнерные модули имеют следующие режимы поведения и характеристики:  
  
-   Их метаданные для всех составных вложенных модулей объединяются друг с другом.  
  
-   Имена типов можно изменять.  
  
-   [ICorDebugModule::GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) возвращает путь к модулю на диске.  
  
-   [ICorDebugModule::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) возвращает размер данного образа.  
  
-   Метод ICorDebugAssembly3.EnumerateContainedAssemblies перечисляет вложенные модули.  
  
-   Метод ICorDebugAssembly3.GetContainerAssembly возвращает `S_FALSE`.  
  
 Вложенные модули имеют следующие режимы поведения и характеристики:  
  
-   Они имеют сокращенный набор метаданных, соответствующий исходной сборке, которая была объединена.  
  
-   Имена метаданных не изменяются.  
  
-   Маловероятно, что токены метаданных будут совпадать с токенами в исходной сборке перед тем, как она была объединена в процессе построения.  
  
-   [ICorDebugModule::GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) метод возвращает имя сборки, а не путь к файлу.  
  
-   [ICorDebugModule::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) метод возвращает размер исходного (разъединенного) образа.  
  
-   Метод ICorDebugModule3.EnumerateContainedAssemblies возвращает `S_FALSE`.  
  
-   Метод ICorDebugAssembly3.GetContainerAssembly возвращает составной модуль.  
  
## <a name="interfaces-retrieved-from-modules"></a>Интерфейсы, извлеченные из модулей  
 Из модулей можно создать или извлечь различные интерфейсы. Некоторые из них указаны ниже:  
  
-   ICorDebugClass объекта, который возвращается методом [ICorDebugModule::GetClassFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md) метод.  
  
-   ICorDebugAssembly объекта, который возвращается методом [ICorDebugModule::GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) метод.  
  
 Эти объекты всегда кэшируются методом [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md), и они будут иметь один и тот же идентификатор указателя, независимо от того, независимо от того, были ли они созданы или запрошены из контейнерного или вложенного модуля. Вложенный модуль обеспечивает отфильтрованное представление этих кэшированных объектов, но не отдельный кэш со своими собственными копиями.  
  
<a name="APIs"></a>   
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a>Разделение виртуальных модулей и неуправляемые интерфейсы API отладки  
 В следующей таблице показано, как разделение виртуальных модулей влияет на поведение других методов в неуправляемом интерфейсе API отладки.  
  
|Метод|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[ICorDebugFunction::GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Возвращает вложенный модуль, в котором эта функция была изначально определена|Возвращает контейнерный модуль, в который была добавлена эта функция|  
|[ICorDebugClass::GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Возвращает вложенный модуль, в котором этот класс был изначально определен.|Возвращает контейнерный модуль, в который был добавлен этот класс.|  
|ICorDebugModuleDebugEvent::GetModule|Возвращает контейнерный модуль, который был загружен. Независимо от данного параметра, вложенные модули не получают события загрузки.|Возвращает контейнерный модуль, который был загружен.|  
|[ICorDebugAppDomain::EnumerateAssemblies](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Возвращает перечень сборочных узлов и регулярных сборок; контейнерные сборки не включаются. **Примечание:** Если любой контейнерной сборке отсутствуют символы, ни один из его сборочные узлы будут перечислены. Если в любой регулярной сборке отсутствуют символы, то она может быть перечислена или не перечислена.|Возвращает перечень контейнерных сборок и регулярных сборок; сборочные узлы не включаются. **Примечание:** Если любой регулярной сборке отсутствуют символы, он может или не может быть перечислено.|  
|[ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md) (применительно к только IL-код)|Возвращает IL-код, который будет действителен в образе сборки перед слиянием. В частности, любыми правильными встроенными токенами метаданных будут TypeRef или MemberRef, когда типы, на которые выполняется ссылка, не определены в виртуальном модуле, содержащем IL-код. Эти токены TypeRef или MemberRef можно искать [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) соответствующий виртуальный объект ICorDebugModule.|Возвращает IL-код в образе сборки после слияния.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
