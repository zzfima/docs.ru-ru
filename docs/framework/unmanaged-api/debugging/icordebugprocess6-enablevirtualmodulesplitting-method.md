---
title: Метод ICorDebugProcess6::EnableVirtualModuleSplitting
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
ms.openlocfilehash: 32648f40046959ffd8676fe67a1e0a123b0e801f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123506"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a>Метод ICorDebugProcess6::EnableVirtualModuleSplitting
Позволяет включить или отключить разделение виртуальных модулей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `enableSplitting`  
 `true`, чтобы включить разделение виртуальных модулей; `false`, чтобы отключить его.  
  
## <a name="remarks"></a>Заметки  
 Разделение виртуальных [модулей заставляет препроцессор](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) распознать модули, Объединенные в ходе процесса сборки, и представлять их как группу отдельных модулей, а не один большой модуль. Это изменяет поведение различных методов [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , описанных ниже.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
 Этот метод может быть вызван, и значение `enableSplitting` может быть изменено, в любое время. Он не вызывает функциональных изменений с отслеживанием состояния в объекте [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , кроме изменения поведения методов, перечисленных в разделе [разделение виртуального модуля, и раздела API неуправляемой отладки](#APIs) в момент их вызова. Применение виртуальных модулей приводит к ухудшению производительности при вызове этих методов. Кроме того, для правильной реализации интерфейсов [API интерфейса](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) пользователя может потребоваться значительное кэширование в памяти, и эти кэши могут храниться даже после выключения разделения виртуальных модулей.  
  
## <a name="terminology"></a>Терминология  
 При описании разделения виртуальных модулей используются следующие термины:  
  
 контейнерные модули или контейнеры  
 Агрегатные модули.  
  
 вложенные модули или виртуальные модули  
 Модули, находящиеся в контейнере.  
  
 обычные модули  
 Модули, которые не были объединены во время построения. Они не являются ни вложенными, ни контейнерными модулями.  
  
 И модули контейнеров, и подмодули представлены объектами интерфейса ICorDebugModule. Однако в каждом случае поведение интерфейса немного различается, так как в разделе \<x-ref to > описывается раздел.  
  
## <a name="modules-and-assemblies"></a>Модули и сборки  
 Сборки с несколькими модулями не поддерживаются для сценариев объединения сборок, поэтому существует однозначное соответствие между модулем и сборкой. Каждый объект ICorDebugModule, независимо от того, представляет ли он модуль контейнера или вспомогательный модуль, имеет соответствующий объект ICorDebugAssembly. Метод [ICorDebugModule:: Assembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) преобразует из модуля в сборку. Для отображения в другом направлении метод [ICorDebugAssembly:: енумератемодулес](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md) перечисляет только 1 модуль. Так как сборка и модуль образуют в данном случае тесно связанную пару, термины «сборка и модуль» становятся в значительной степени взаимозаменяемыми.  
  
## <a name="behavioral-differences"></a>Различия в поведении  
 Контейнерные модули имеют следующие режимы поведения и характеристики:  
  
- Их метаданные для всех составных вложенных модулей объединяются друг с другом.  
  
- Имена типов можно изменять.  
  
- Метод [ICorDebugModule::-Name](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) Возвращает путь к модулю на диске.  
  
- Метод [ICorDebugModule:: resize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) возвращает размер этого изображения.  
  
- Метод ICorDebugAssembly3.EnumerateContainedAssemblies перечисляет вложенные модули.  
  
- Метод ICorDebugAssembly3.GetContainerAssembly возвращает `S_FALSE`.  
  
 Вложенные модули имеют следующие режимы поведения и характеристики:  
  
- Они имеют сокращенный набор метаданных, соответствующий исходной сборке, которая была объединена.  
  
- Имена метаданных не изменяются.  
  
- Маловероятно, что токены метаданных будут совпадать с токенами в исходной сборке перед тем, как она была объединена в процессе построения.  
  
- Метод [ICorDebugModule::-Name](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) возвращает имя сборки, а не путь к файлу.  
  
- Метод [ICorDebugModule:: resize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) возвращает исходный необъединенный размер изображения.  
  
- Метод ICorDebugModule3.EnumerateContainedAssemblies возвращает `S_FALSE`.  
  
- Метод ICorDebugAssembly3.GetContainerAssembly возвращает составной модуль.  
  
## <a name="interfaces-retrieved-from-modules"></a>Интерфейсы, извлеченные из модулей  
 Из модулей можно создать или извлечь различные интерфейсы. Некоторые из них указаны ниже:  
  
- Объект ICorDebugClass, возвращаемый методом [ICorDebugModule:: жетклассфромтокен](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md) .  
  
- Объект ICorDebugAssembly, возвращаемый методом [ICorDebugModule::](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) GetObject.  
  
 Эти объекты всегда кэшируются в [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md), и они будут иметь одинаковое удостоверение указателя независимо от того, были ли они созданы или запрошены из модуля контейнера или из подмодуля. Вложенный модуль обеспечивает отфильтрованное представление этих кэшированных объектов, но не отдельный кэш со своими собственными копиями.  
  
<a name="APIs"></a>   
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a>Разделение виртуальных модулей и неуправляемые интерфейсы API отладки  
 В следующей таблице показано, как разделение виртуальных модулей влияет на поведение других методов в неуправляемом интерфейсе API отладки.  
  
|Метод|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[ICorDebugFunction:: module](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Возвращает вложенный модуль, в котором эта функция была изначально определена|Возвращает контейнерный модуль, в который была добавлена эта функция|  
|[ICorDebugClass:: module](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Возвращает вложенный модуль, в котором этот класс был изначально определен.|Возвращает контейнерный модуль, в который был добавлен этот класс.|  
|ICorDebugModuleDebugEvent::GetModule|Возвращает контейнерный модуль, который был загружен. Независимо от данного параметра, вложенные модули не получают события загрузки.|Возвращает контейнерный модуль, который был загружен.|  
|[ICorDebugAppDomain:: EnumerateAssemblies](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Возвращает перечень сборочных узлов и регулярных сборок; контейнерные сборки не включаются. **Примечание.**  Если в любой сборке контейнера отсутствуют символы, ни одна из ее вложенных сборок не будет перечисляться. Если в любой регулярной сборке отсутствуют символы, то она может быть перечислена или не перечислена.|Возвращает перечень контейнерных сборок и регулярных сборок; сборочные узлы не включаются. **Примечание.**  Если в любой обычной сборке отсутствуют символы, она может быть или не перечисляться.|  
|[ICorDebugCode::-Code](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md) (при ссылке только на код IL)|Возвращает IL-код, который будет действителен в образе сборки перед слиянием. В частности, любыми правильными встроенными токенами метаданных будут TypeRef или MemberRef, когда типы, на которые выполняется ссылка, не определены в виртуальном модуле, содержащем IL-код. Эти токены TypeRef или MemberRef можно искать в объекте [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) для соответствующего виртуального объекта ICorDebugModule.|Возвращает IL-код в образе сборки после слияния.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
