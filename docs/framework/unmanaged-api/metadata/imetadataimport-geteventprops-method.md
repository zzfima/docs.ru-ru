---
title: Метод IMetaDataImport::GetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177271"
---
# <a name="imetadataimportgeteventprops-method"></a>Метод IMetaDataImport::GetEventProps
Получает информацию о метаданных для события, представленную указанным маркером события, включая тип декларирования, способы добавления и удаления для делегатов, а также любые флаги и другие связанные данные.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,
   [out] LPCWSTR       szEvent,
   [in]  ULONG         cchEvent,
   [out] ULONG         *pchEvent,
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,
   [out] mdMethodDef   *pmdRemoveOn,
   [out] mdMethodDef   *pmdFire,
   [out] mdMethodDef   rmdOtherMethod[],
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ev`  
 (в) Токен метаданных события, представляющий событие для получения метаданных.  
  
 `pClass`  
 (ваут) Указатель на маркер TypeDef, представляющий класс, объявляющий событие.  
  
 `szEvent`  
 (ваут) Название события, на которое `ev`ссылается .  
  
 `pchEvent`  
 (в) Запрошенная длина в широких `szEvent`символах .  
  
 `pdwEventFlags`  
 (ваут) Возвращается длина в `szEvent`широких символов .  
  
 `ptkEventType`  
 (ваут) Указатель на маркер метаданных TypeRef или TypeDef, представляющий <xref:System.Delegate> тип события.  
  
 `pmdAddOn`  
 (ваут) Указатель на маркер метаданных, представляющий метод, который добавляет обработчики для события.  
  
 `pmdRemoveOn`  
 (ваут) Указатель на маркер метаданных, представляющий метод, удаляющий обработчики для события.  
  
 `pmdFire`  
 (ваут) Указатель на маркер метаданных, представляющий метод, повысивший событие.  
  
 `rmdOtherMethod`  
 (ваут) Массив указателей токенов на другие методы, связанные с событием.  
  
 `cMax`  
 [in] Максимальный размер массива `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 (ваут) Количество возвращенных токенов `rmdOtherMethod`в .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
