---
title: "Метод IMetaDataDispenserEx::SetOption"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 96810ba0eab99d1df58f0b68b85ef4da8ce7084e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexsetoption-method"></a>Метод IMetaDataDispenserEx::SetOption
Устанавливает для указанного параметра заданное значение для текущей области метаданных. Параметр определяет способ обработки вызовов текущей области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `optionId`  
 [in] Указатель на идентификатор GUID, который указывает параметр должен иметь значение.  
  
 `pValue`  
 [in] Значение, используемое для задания параметра. Тип этого значения должен быть разновидностью указанного параметра.  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице перечислены доступные идентификаторы GUID, `optionId` может указывать параметр и соответствующие допустимые значения для `pValue` параметра.  
  
|GUID|Описание:|`pValue`Параметр|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Определяет, какие элементы проверяются на наличие дубликатов. Каждый раз при вызове [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) метод, который создает новый элемент, вы можете запросить метод для проверки, является ли элемент уже существует в текущей области. Например, можно проверить наличие `mdMethodDef` элементы; в этом случае при вызове [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), она проверяет, что метод уже существует в текущей области. Эта проверка используется ключ, который однозначно определяет данный метод: родительский тип, имя и подпись.|Должен быть разновидностью UI4 и должен состоять из комбинации значений [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) перечисления.|  
|MetaDataRefToDefCheck|Элементы управления, которые ссылки на элементы, преобразуемые в определения. По умолчанию ядро метаданных будет оптимизировать код, преобразование ссылочного элемента его определение, если указанный элемент, фактически определенных в текущей области.|Должен быть разновидностью UI4 и должен состоять из комбинации значений [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) перечисления.|  
|MetaDataNotificationForTokenMovement|Задает, какой токен, происходящее при слиянии метаданных создает обратные вызовы. Используйте [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) метод, чтобы установить вашей [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) интерфейса.|Должен быть разновидностью UI4 и должен состоять из комбинации значений [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) перечисления.|  
|MetaDataSetENC|Управляет поведением edit and continue (ENC). Одновременно можно задать только один режим работы.|Должен быть разновидностью UI4 и должен содержать значение [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) перечисления. Значение не является битовой маской.|  
|MetaDataErrorIfEmitOutOfOrder|Элементы управления, какие ошибки создается out порядок создания обратных вызовов. Выдача метаданных по порядку не является неустранимой; Однако если вы предоставлять метаданные в порядке их предпочитаемую ядром метаданных, метаданные является более компактным и таким образом можно повысить эффективность поиска. Используйте `IMetaDataEmit::SetHandler` метод, чтобы установить вашей [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) интерфейса.|Должен быть разновидностью UI4 и должен состоять из комбинации значений [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) перечисления.|  
|MetaDataImportOption|Определяет, какие типы элементов, которые были удалены в процессе ENC извлекаются при помощи перечислителя.|Должен быть разновидностью UI4 и должен состоять из комбинации значений [перечисление CorImportOptions](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) перечисления.|  
|MetaDataThreadSafetyOptions|Управляет ли ядро метаданных получает модулей чтения/записи блокировки, обеспечивая безопасность потоков. По умолчанию в ядре предполагается, что доступа является однопоточным вызывающим объектом, поэтому блокировки не создаются. Клиенты отвечают за обслуживание надлежащего выполнения синхронизации потока при использовании API метаданных.|Должен быть разновидностью UI4 и должен содержать значение [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) перечисления. Значение не является битовой маской.|  
|MetaDataGenerateTCEAdapters|Определяет, должна ли программа импорта библиотек типов создавать адаптеры тесно связанных событий (TCE) для контейнеров точек подключения COM.|Должен быть разновидностью типа BOOL. Если `pValue` равно `true`, программа импорта библиотек типов создает адаптеры TCE.|  
|MetaDataTypeLibImportNamespace|Задает другие пространства имен для библиотеки типов, импортируемой.|Необходимо значение null или является разновидностью типа BSTR. Если `pValue` имеет значение null, текущее пространство имен имеет значение null; в противном случае, текущего пространства имен имеет значение в строку, которая хранится в разновидности типа BSTR.|  
|MetaDataLinkerOptions|Определяет, должен ли компоновщик создать сборку или файл модуля .NET Framework.|Должен быть разновидностью UI4 и должен состоять из комбинации значений [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) перечисления.|  
|MetaDataRuntimeVersion|Указывает версию среды CLR, для которого был создан этот образ. Версия сохраняется в виде строки, например «v1.0.3705».|Должно быть значение null, значение VT_EMPTY или разновидностью BSTR. Если `pValue` является null, для версии среды выполнения устанавливается значение null. Если `pValue` равно VT_EMPTY, версия устанавливается в значение по умолчанию, которое выводится из версии Mscorwks.dll, в течение которого выполняется код метаданных. В противном случае — версия среды выполнения имеет значение в строку, которая хранится в разновидности типа BSTR.|  
|MetaDataMergerOptions|Задает параметры для слияния метаданных.|Должен быть разновидностью UI4 и должен состоять из комбинации значений `MergeFlags` перечисления, который описан в файле CorHdr.h.|  
|MetaDataPreserveLocalRefs|Отключение оптимизации локальных ссылок в определения.|Должен состоять из комбинации значений [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) перечисления.|  
  
## <a name="requirements"></a>Требования  
 **Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [Интерфейс IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
