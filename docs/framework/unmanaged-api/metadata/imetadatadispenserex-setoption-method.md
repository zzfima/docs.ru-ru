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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9869efee18549c3d0c8b9ee9ca27cf31c1ccf452
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050146"
---
# <a name="imetadatadispenserexsetoption-method"></a>Метод IMetaDataDispenserEx::SetOption
Задает указанному параметру заданное значение для текущей области метаданных. Параметр определяет, как обрабатываются вызовы к текущей области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `optionId`  
 [in] Указатель на идентификатор GUID, который указывает параметр должен иметь значение.  
  
 `pValue`  
 [in] Значение, используемое для задания параметра. Тип этого значения должен быть вариант указанного параметра типа.  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице перечислены доступные идентификаторы GUID, `optionId` может указывать параметр и его соответствующий допустимых значений для `pValue` параметра.  
  
|Идентификатор GUID|Описание|`pValue` Параметр|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Определяет, какие элементы проверяются на наличие дубликатов. Каждый раз при вызове [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) метод, который создает новый элемент, вы можете задавать способ проверить, существует ли уже элемент в текущей области. Например, можно проверить существование `mdMethodDef` элементов; в этом случае при вызове [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), он проверит, что метод уже существует в текущей области. Эта проверка используется ключ, который однозначно определяет данный метод: родительский тип, имя и подпись.|Должен быть разновидностью UI4 и должен содержать сочетание значений [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) перечисления.|  
|MetaDataRefToDefCheck|Определяет, какие товары преобразуются в определения. По умолчанию подсистема метаданных будет оптимизировать код путем преобразования к его определению ссылочного элемента, если указанный элемент определен в текущей области.|Должен быть разновидностью UI4 и должен содержать сочетание значений [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) перечисления.|  
|MetaDataNotificationForTokenMovement|Элементы управления, токена, происходящее во время слияния метаданных создавать обратные вызовы. Используйте [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) метод, чтобы установить ваш [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) интерфейс.|Должен быть разновидностью UI4 и должен содержать сочетание значений [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) перечисления.|  
|MetaDataSetENC|Управляет поведением изменить и продолжить "(ENC). Одновременно можно задать только один режим работы.|Должен быть разновидностью UI4 и должно содержать значение [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) перечисления. Значение не является битовой маской.|  
|MetaDataErrorIfEmitOutOfOrder|Элементы управления, какие ошибки генерируется out порядке создавать обратные вызовы. Выдача метаданных по порядку не является неустранимой; Тем не менее если вы выпустить метаданных в порядке, который имеет больший приоритет, подсистемой метаданных, метаданных является более компактным и таким образом можно повысить эффективность поиска. Используйте `IMetaDataEmit::SetHandler` метод, чтобы установить ваш [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) интерфейс.|Должен быть разновидностью UI4 и должен содержать сочетание значений [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) перечисления.|  
|MetaDataImportOption|Определяет, какие виды элементов, которые были удалены во время ENC извлекаются путем перечислитель.|Должен быть разновидностью UI4 и должен содержать сочетание значений [перечисление CorImportOptions](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) перечисления.|  
|MetaDataThreadSafetyOptions|Управляет ли подсистема метаданных получает потоков чтения/записи блокировок, обеспечивая безопасность потоков. По умолчанию в ядре предполагается, что доступ является однопоточным вызывающим объектом, поэтому блокировки не создаются. Клиенты отвечают за обеспечение надлежащего выполнения синхронизации потока, при использовании API метаданных.|Должен быть разновидностью UI4 и должно содержать значение [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) перечисления. Значение не является битовой маской.|  
|MetaDataGenerateTCEAdapters|Определяет, должна ли программа импорта библиотек типов создавать адаптеры тесно связанных событий (TCE) для контейнеров точек подключения COM.|Должен быть разновидностью типа BOOL. Если `pValue` присваивается `true`, программа импорта библиотек типов создает адаптеры TCE.|  
|MetaDataTypeLibImportNamespace|Задает пространство имен не по умолчанию для библиотеки типов, импортируемой.|Должен быть либо значение null, либо вариант типа BSTR. Если `pValue` имеет значение null, текущее пространство имен имеет значение null; в противном случае, текущее пространство имен задается строка, которая хранится в разновидности типа BSTR.|  
|MetaDataLinkerOptions|Определяет, должен ли компоновщик создать сборку или файл модуля .NET Framework.|Должен быть разновидностью UI4 и должен содержать сочетание значений [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) перечисления.|  
|MetaDataRuntimeVersion|Указывает версию среды CLR, относительно которой построена этот образ. Версия сохраняется в виде строки, например «v1.0.3705».|Должно быть значение null, значение VT_EMPTY или разновидностью BSTR. Если `pValue` имеет значение null, для версии среды выполнения устанавливается значение null. Если `pValue` — VT_EMPTY, версия будет присвоено значение по умолчанию, которое извлекается из версии "Mscorwks.dll", в течение которого выполняется код метаданных. В противном случае — ту версию среды выполнения присваивается строка, которая хранится в разновидности типа BSTR.|  
|MetaDataMergerOptions|Задает параметры для слияния метаданных.|Должен быть разновидностью UI4 и должен содержать сочетание значений `MergeFlags` перечисления, который описан в файле CorHdr.h.|  
|MetaDataPreserveLocalRefs|Отключение оптимизации локальные ссылки в определения.|Должен содержать сочетание значений [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) перечисления.|  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
