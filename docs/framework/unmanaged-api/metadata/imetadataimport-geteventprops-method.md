---
title: "Метод IMetaDataImport::GetEventProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetEventProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9f616e00d79aec864bbb50b168a17e3f131a1aa1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgeteventprops-method"></a>Метод IMetaDataImport::GetEventProps
Возвращает сведения о метаданных для события, представленного указанным токеном события, включая объявляющий тип, добавления и методы удаления для делегатов и всевозможные флаги и другие связанные с ними данные.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `ev`  
 [in] Токен метаданных события, представляющий событие для получения метаданных для.  
  
 `pClass`  
 [out] Указатель на токен TypeDef, представляющий класс, объявляющий событие.  
  
 `szEvent`  
 [out] Имя события, на который указывает `ev`.  
  
 `pchEvent`  
 [in] Запрошенная длина в расширенных символах с `szEvent`.  
  
 `pdwEventFlags`  
 [out] Возвращаемая длина в расширенных символах с `szEvent`.  
  
 `ptkEventType`  
 [out] Указатель на объект TypeRef или TypeDef метаданных токен, представляющий <xref:System.Delegate> тип события.  
  
 `pmdAddOn`  
 [out] Указатель на токен метаданных, представляющий метод, который добавляет обработчик для события.  
  
 `pmdRemoveOn`  
 [out] Указатель на токен метаданных, представляющий метод, который удаляет обработчик для события.  
  
 `pmdFire`  
 [out] Указатель на токен метаданных, представляющий метод, который вызывает событие.  
  
 `rmdOtherMethod`  
 [out] Массив указателей токена в другие методы, связанные с событием.  
  
 `cMax`  
 [in] Максимальный размер массива `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 [out] Число маркеров, возвращаемых в `rmdOtherMethod`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
