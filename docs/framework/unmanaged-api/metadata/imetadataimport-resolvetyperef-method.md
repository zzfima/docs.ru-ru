---
title: "Метод IMetaDataImport::ResolveTypeRef"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64a783297b27c9d1400670eecb7dfe4cb69c2b96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="1cf8b-102">Метод IMetaDataImport::ResolveTypeRef</span><span class="sxs-lookup"><span data-stu-id="1cf8b-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="1cf8b-103">Разрешает <xref:System.Type> ссылку, представленный указанный токен TypeRef.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cf8b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cf8b-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1cf8b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1cf8b-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="1cf8b-106">[in] Токен метаданных TypeRef для возврата сведений о типе, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="1cf8b-107">[in] Идентификатор IID интерфейса, чтобы вернуться в `ppIScope`.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="1cf8b-108">Как правило это будет IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="1cf8b-109">[out] Интерфейс для области модуля, в которой определен тип, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="1cf8b-110">[out] Указатель на маркер TypeDef, который представляет ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cf8b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1cf8b-111">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1cf8b-112">Не используйте этот метод, если загружено несколько доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="1cf8b-113">Метод не влияют на границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="1cf8b-114">Если несколько версий сборки загружаются, и они содержат того же типа с тем же пространством имен, метод возвращает области модуля найденную первого типа.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="1cf8b-115">`ResolveTypeRef` Метод выполняет поиск определения типа в других модулях.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="1cf8b-116">Если найден в определении типа `ResolveTypeRef` возвращает интерфейс для области модуля, а также токен TypeDef для типа.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="1cf8b-117">Если ссылка на тип разрешения имеет разрешение области AssemblyRef, `ResolveTypeRef` метод ищет совпадение только в области метаданных, которые уже открыт с помощью вызовов [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)метода или [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="1cf8b-118">Это вызвано `ResolveTypeRef` не удается определить из области AssemblyRef, где на диске или в глобальном кэше сборок хранится сборка.</span><span class="sxs-lookup"><span data-stu-id="1cf8b-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cf8b-119">Требования</span><span class="sxs-lookup"><span data-stu-id="1cf8b-119">Requirements</span></span>  
 <span data-ttu-id="1cf8b-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cf8b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cf8b-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1cf8b-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1cf8b-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1cf8b-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1cf8b-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cf8b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cf8b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="1cf8b-124">See Also</span></span>  
 [<span data-ttu-id="1cf8b-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1cf8b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="1cf8b-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1cf8b-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
