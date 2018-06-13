---
title: Метод IMetaDataImport::ResolveTypeRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 106ef520f64233323cbb3f26cb3efdee152559b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449485"
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
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
