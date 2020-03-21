---
title: Метод IMetaDataDispenserEx::SetOption
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.SetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type:
- apiref
ms.openlocfilehash: f8e85a670d04e5825653864484b7ccd9ce747949
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175906"
---
# <a name="imetadatadispenserexsetoption-method"></a>Метод IMetaDataDispenserEx::SetOption
Устанавливает указанный вариант к заданной стоимости для текущей области метаданных. Опция контролирует обработку вызовов в текущую область метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetOption (  
    [in] REFGUID optionId,
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `optionId`  
 (в) Указатель на GUID, который определяет возможность, которая будет установлена.  
  
 `pValue`  
 (в) Значение для установки опции. Тип этого значения должен быть вариантом указанного параметра.  
  
## <a name="remarks"></a>Remarks  
 В следующей таблице перечислены доступные GUID, на которые `optionId` параметр `pValue` может указать, и соответствующие допустимые значения для параметра.  
  
|GUID|Описание|`pValue`Параметр|  
|----------|-----------------|------------------------|  
|MetaDataCheckМилидаксДля|Элементы управления, какие элементы проверяются на наличие дубликатов. Каждый раз, когда вы вызываете метод [IMetaDataEmit,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) который создает новый элемент, вы можете задать метод, чтобы проверить, существует ли элемент уже в текущей области. Например, можно проверить наличие `mdMethodDef` элементов; в этом случае, когда вы звоните [IMetaDataEmit: :DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), он будет проверять, что метод еще не существует в текущем объеме. В этой проверке используется ключ, который однозначно идентифицирует данный метод: тип родителя, имя и подпись.|Должен быть вариант типа UI4, и должен содержать комбинацию значений [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) перечисления.|  
|MetaDataRefToDefCheck|Элементы управления, на которые ссылаются элементы, преобразуются в определения. По умолчанию движок метаданных оптимизирует код путем преобразования ссылки на элемент в его определение, если ссылка на элемент фактически определена в текущей области.|Должен быть вариант типа UI4, и должен содержать комбинацию значений [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) перечисления.|  
|MetaDataNotificationForTo|Элементы управления, которые маркеры remaps происходит во время слияния метаданных генерировать обратные вызовы. Используйте метод [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) для создания интерфейса [IMapToken.](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)|Должен быть вариант типа UI4, и должен содержать комбинацию значений [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) перечисления.|  
|MetaDataSetENC|Контролирует поведение изменения и продолжения (ENC). Одновременно можно установить только один режим поведения.|Должен быть вариант типа UI4, и должен содержать значение [перечисления CorSetENC.](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) Значение не битмаска.|  
|MetaDataErrorIfEmitOutOrder|Элементы управления, испускаемые ошибками вне заказа, генерируют обратные вызовы. Излучение метаданных не является фатальным; однако, если вы испускаете метаданные в порядке, который благоприятствует движку метаданных, метаданные более компактны и, следовательно, могут быть более эффективно искали. Используйте `IMetaDataEmit::SetHandler` метод для создания [интерфейса IMetaDataError.](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)|Должен быть вариант типа UI4, и должен содержать комбинацию значений [CorErrorEmitOutOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) перечисления.|  
|MetaDataИмпортOption|Контролирует, какие элементы, которые были удалены во время ENC, извлекаются регистратором.|Должен быть вариант типа UI4, и должен содержать комбинацию значений [перечисления CorImportOptions Enumeration.](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md)|  
|MetaDataThreadSafetyOptions|Контролирует, получает ли движок метаданных блокировки чтения/писателя, обеспечивая тем самым безопасность потока. По умолчанию движок предполагает, что доступ является однопонивным абонентом, поэтому блокировки не получены. Клиенты несут ответственность за поддержание правильной синхронизации потоков при использовании API метаданных.|Должен быть вариант типа UI4, и должен содержать значение [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) перечисления. Значение не битмаска.|  
|MetaDataGenerateTCEAdapters|Контролирует, должен ли импортер библиотеки типа создавать адаптеры плотно связанных событий (TCE) для контейнеров точек соединения COM.|Должен быть вариант типа BOOL. Если `pValue` настроен `true`на то, то импортер библиотеки типа генерирует адаптеры TCE.|  
|MetaDataTypeLibИмпортНо-пространство|Определяет пространство непо умолчанию для импортируемой библиотеки типов.|Должно быть либо нулевая стоимость, либо вариант типа BSTR. Если `pValue` значение является нулевым, то текущее пространство имен будет сведено к нулю; в противном случае текущее пространство имен устанавливается в строку, которая удерживается в типе BSTR варианта.|  
|MetaDataLinkerOptions|Контролирует, должен ли связующий создать сборку или модуль ный файл .NET Framework.|Должен быть вариант типа UI4, и должен содержать комбинацию значений [corLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) перечисления.|  
|MetaDataRuntimeVersion|Определяет версию общего времени выполнения языка, на котором было построено это изображение. Версия хранится в виде строки, например "v1.0.3705".|Должно быть нулевая стоимость, VT_EMPTY значение или вариант типа BSTR. Если `pValue` версия времени выполнения недействительна. Если `pValue` VT_EMPTY, версия устанавливается в значение по умолчанию, которое взято из версии Mscorwks.dll, в которой работает код метаданных. В противном случае версия времени выполнения устанавливается на строку, которая удерживается в типе BSTR варианта.|  
|MetaDataMergerOptions|Определяет варианты слияния метаданных.|Должен быть вариант типа UI4, и должен содержать комбинацию `MergeFlags` значений перечисления, которая описана в файле CorHdr.h.|  
|MetaDataPreserveLocalRefs|Отпугиваюает оптимизацию локальных ссылок в определениях.|Должно содержаться сочетание значений перечисления [CorLocalRefConservation.](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md)|  
  
## <a name="requirements"></a>Требования  
 **Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
