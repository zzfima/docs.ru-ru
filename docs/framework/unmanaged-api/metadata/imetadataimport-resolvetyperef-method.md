---
title: "Метод IMetaDataImport::ResolveTypeRef"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.ResolveTypeRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 390387abef5c48b4842adcfbfca126bb8292cc28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportresolvetyperef-method"></a>Метод IMetaDataImport::ResolveTypeRef
Разрешает <xref:System.Type> ссылку, представленный указанный токен TypeRef.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tr`  
 [in] Токен метаданных TypeRef для возврата сведений о типе, на которую указывает ссылка.  
  
 `riid`  
 [in] Идентификатор IID интерфейса, чтобы вернуться в `ppIScope`. Как правило это будет IID_IMetaDataImport.  
  
 `ppIScope`  
 [out] Интерфейс для области модуля, в которой определен тип, на который указывает ссылка.  
  
 `ptd`  
 [out] Указатель на маркер TypeDef, который представляет ссылочного типа.  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
>  Не используйте этот метод, если загружено несколько доменов приложений. Метод не влияют на границы домена приложения. Если несколько версий сборки загружаются, и они содержат того же типа с тем же пространством имен, метод возвращает области модуля найденную первого типа.  
  
 `ResolveTypeRef` Метод выполняет поиск определения типа в других модулях. Если найден в определении типа `ResolveTypeRef` возвращает интерфейс для области модуля, а также токен TypeDef для типа.  
  
 Если ссылка на тип разрешения имеет разрешение области AssemblyRef, `ResolveTypeRef` метод ищет совпадение только в области метаданных, которые уже открыт с помощью вызовов [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)метода или [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) метод. Это вызвано `ResolveTypeRef` не удается определить из области AssemblyRef, где на диске или в глобальном кэше сборок хранится сборка.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
