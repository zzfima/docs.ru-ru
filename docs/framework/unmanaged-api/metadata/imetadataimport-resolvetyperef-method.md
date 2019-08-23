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
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="977f6-102">Метод IMetaDataImport::ResolveTypeRef</span><span class="sxs-lookup"><span data-stu-id="977f6-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="977f6-103">Разрешает <xref:System.Type> ссылку, представленную указанным токеном TypeRef.</span><span class="sxs-lookup"><span data-stu-id="977f6-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="977f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="977f6-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="977f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="977f6-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="977f6-106">окне Токен метаданных TypeRef для возврата сведений о типе, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="977f6-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="977f6-107">окне IID интерфейса, в `ppIScope`котором возвращается.</span><span class="sxs-lookup"><span data-stu-id="977f6-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="977f6-108">Как правило, это IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="977f6-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="977f6-109">заполняет Интерфейс к области модуля, в которой определен ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="977f6-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="977f6-110">заполняет Указатель на маркер TypeDef, представляющий ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="977f6-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="977f6-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="977f6-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="977f6-112">Не используйте этот метод, если загружено несколько доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="977f6-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="977f6-113">Метод не учитывает границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="977f6-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="977f6-114">Если загружено несколько версий сборки и они содержат один и тот же тип с одним и тем же пространством имен, метод возвращает область действия модуля первого найденного типа.</span><span class="sxs-lookup"><span data-stu-id="977f6-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="977f6-115">`ResolveTypeRef` Метод выполняет поиск определения типа в других модулях.</span><span class="sxs-lookup"><span data-stu-id="977f6-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="977f6-116">Если обнаружено определение типа, `ResolveTypeRef` возвращает интерфейс для этой области модуля, а также маркер TypeDef для типа.</span><span class="sxs-lookup"><span data-stu-id="977f6-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="977f6-117">Если разрешенная ссылка на тип имеет область определения AssemblyRef, `ResolveTypeRef` метод выполняет поиск совпадения только в областях метаданных, которые уже открыты с вызовами метода [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) или [ Метод IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="977f6-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="977f6-118">Это связано с `ResolveTypeRef` тем, что не может определить только из области AssemblyRef, в которой хранится сборка на диске или в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="977f6-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="977f6-119">Требования</span><span class="sxs-lookup"><span data-stu-id="977f6-119">Requirements</span></span>  
 <span data-ttu-id="977f6-120">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="977f6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="977f6-121">**Заголовок.** COR. h</span><span class="sxs-lookup"><span data-stu-id="977f6-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="977f6-122">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="977f6-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="977f6-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="977f6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="977f6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="977f6-124">See also</span></span>

- [<span data-ttu-id="977f6-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="977f6-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="977f6-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="977f6-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
