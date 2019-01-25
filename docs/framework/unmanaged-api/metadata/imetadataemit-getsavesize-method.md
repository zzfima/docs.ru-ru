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
ms.openlocfilehash: 164cdc5c04a55e9c33dda51e10dfb37f38ec1b6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746548"
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
 [in] Значение [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) перечисление, указывающее, следует ли получить точное или приблизительное размер. Допустимы только три значения: cssAccurate, cssQuick и cssDiscardTransientCAs:  
  
-   cssAccurate возвращает точный размер сохранения, но требует больше времени для вычисления.  
  
-   cssQuick возвращает размер в целях безопасности, но занимает меньше времени, для которого требуется вычислить.  
  
-   сообщает cssDiscardTransientCAs `GetSaveSize` , может возникнуть исключение сейчас присваиваются значения настраиваемых атрибутов.  
  
 `pdwSaveSize`  
 [out] Указатель на размер, необходимый для сохранения файла.  
  
## <a name="remarks"></a>Примечания  
 `GetSaveSize` вычисляет размер, в байтах, чтобы сохранить сборку и все метаданные в текущей области. (Вызов [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) метод выдаст это число байтов.)  
  
 Если вызывающий объект реализует [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) интерфейса (через [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) или [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` выполняет два прохода по метаданным для оптимизации и сжатия. В противном случае оптимизация не выполняется.  
  
 Если выполнить оптимизацию, первый проход просто сортирует структуры метаданных для настройки производительности поиска во время импорта. Этот шаг обычно приводит к переносу записей, с побочным эффектом, что маркеров, сохраненных с помощью средства для дальнейшего становятся недействительными. Метаданные не сообщающий вызывающему объекту этих изменениях маркера до выполнения второй передачи, тем не менее. На втором этапе выполняются различные операции, которые призваны уменьшить общий размер метаданных, как оптимизация (ранняя привязка) `mdTypeRef` и `mdMemberRef` маркеры, если ссылка указывает на тип или член, объявленный в текущей области метаданных. На этом этапе возникает другой цикл сопоставления маркеров. После этого этапа ядро метаданных уведомляет вызывающего объекта, через его `IMapToken` интерфейс любого изменения значений маркера.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
