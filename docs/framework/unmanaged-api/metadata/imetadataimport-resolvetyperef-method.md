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
ms.openlocfilehash: f323e91e60c9735a51e955eaab6673ca167f294d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951870"
---
# <a name="imetadataimportresolvetyperef-method"></a>Метод IMetaDataImport::ResolveTypeRef
Разрешает <xref:System.Type> ссылку, представленную указанным токеном TypeRef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tr`  
 окне Токен метаданных TypeRef для возврата сведений о типе, на который указывает ссылка.  
  
 `riid`  
 окне IID интерфейса, в `ppIScope`котором возвращается. Как правило, это IID_IMetaDataImport.  
  
 `ppIScope`  
 заполняет Интерфейс к области модуля, в которой определен ссылочный тип.  
  
 `ptd`  
 заполняет Указатель на маркер TypeDef, представляющий ссылочный тип.  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
> Не используйте этот метод, если загружено несколько доменов приложений. Метод не учитывает границы домена приложения. Если загружено несколько версий сборки и они содержат один и тот же тип с одним и тем же пространством имен, метод возвращает область действия модуля первого найденного типа.  
  
 `ResolveTypeRef` Метод выполняет поиск определения типа в других модулях. Если обнаружено определение типа, `ResolveTypeRef` возвращает интерфейс для этой области модуля, а также маркер TypeDef для типа.  
  
 Если разрешенная ссылка на тип имеет область определения AssemblyRef, `ResolveTypeRef` метод выполняет поиск совпадения только в областях метаданных, которые уже открыты с вызовами метода [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) или [ Метод IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) . Это связано с `ResolveTypeRef` тем, что не может определить только из области AssemblyRef, в которой хранится сборка на диске или в глобальном кэше сборок.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** COR. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
