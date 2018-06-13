---
title: Метод IMetaDataEmit::GetSaveSize
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9a65f76aed00e2b848f8603f1fee4d6acc91f99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449161"
---
# <a name="imetadataemitgetsavesize-method"></a>Метод IMetaDataEmit::GetSaveSize
Получает приблизительный двоичный размер сборки и ее метаданные в текущей области.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fSave`  
 [in] Значение [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) перечисления, которое указывает, следует ли получить точное или приблизительное размер. Допустимы только три значения: cssAccurate cssQuick и cssDiscardTransientCAs:  
  
-   cssAccurate возвращает точный размер сохранения, но занимает больше времени для вычисления.  
  
-   cssQuick возвращает размер, для безопасности, но занимает меньше времени для вычисления.  
  
-   сообщает cssDiscardTransientCAs `GetSaveSize` , он может отбрасывание удаляемое настраиваемых атрибутов.  
  
 `pdwSaveSize`  
 [out] Указатель на размер, необходимый для сохранения файла.  
  
## <a name="remarks"></a>Примечания  
 `GetSaveSize` вычисляет размер, в байтах для сохранения сборки и ее метаданные в текущей области. (Вызов [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) метод выдаст это число байтов.)  
  
 Если вызывающий объект реализует интерфейс [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) интерфейса (через [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) или [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` выполняет два прохода через метаданные для оптимизации, а затем сжать. В противном случае оптимизация не выполняется.  
  
 Если выполнить оптимизацию, первый проход просто сортирует структуры метаданных для настройки производительности поиска во время импорта. Этот шаг обычно приводит к перемещению записей относительно с побочным эффектом недействительными маркеров, сохраненных с помощью средства для дальнейшего использования. Метаданные не информирования вызывающего объекта об этих изменениях маркера до выполнения второй передачи, однако. При втором проходе выполняются различные оптимизации, предназначенные для снижения общего объема метаданных, например оптимизация (раннее связывание) `mdTypeRef` и `mdMemberRef` маркеры, если ссылка указывает на тип или член, объявленный в текущей области метаданных. На этом этапе происходит другой цикл сопоставления маркеров. После этого этапа ядро метаданных уведомляет о вызывающем объекте, через его `IMapToken` интерфейс какой-либо изменить значения маркера.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
