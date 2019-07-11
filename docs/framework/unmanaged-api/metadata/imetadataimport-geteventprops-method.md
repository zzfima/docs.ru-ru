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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c87f2212c761dc31a75addabca6970c5497aa2a0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782418"
---
# <a name="imetadataimportgeteventprops-method"></a>Метод IMetaDataImport::GetEventProps
Получает сведения о метаданных для события, представленного указанным токеном события, включая объявляющий тип, добавления и методы удаления для делегатов и все флаги и связанные с ним данные.  
  
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
 [in] Токен метаданных события, представляющий событие для получения метаданных для.  
  
 `pClass`  
 [out] Указатель на токен TypeDef, представляющий класс, объявляющий событие.  
  
 `szEvent`  
 [out] Имя события, который ссылается `ev`.  
  
 `pchEvent`  
 [in] Длина запрошенной в расширенных символах `szEvent`.  
  
 `pdwEventFlags`  
 [out] Возвращаемая длина в расширенных символах `szEvent`.  
  
 `ptkEventType`  
 [out] Указатель на TypeRef или TypeDef метаданных маркер, представляющий <xref:System.Delegate> тип события.  
  
 `pmdAddOn`  
 [out] Указатель на токен метаданных, представляющий метод, который добавляет обработчики для события.  
  
 `pmdRemoveOn`  
 [out] Указатель на токен метаданных, представляющий метод, который удаляет обработчики для события.  
  
 `pmdFire`  
 [out] Указатель на токен метаданных, представляющий метод, который вызывает событие.  
  
 `rmdOtherMethod`  
 [out] Массив токенов указатели на другие методы, связанные с событием.  
  
 `cMax`  
 [in] Максимальный размер массива `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 [out] Число маркеров, возвращаемых в `rmdOtherMethod`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
