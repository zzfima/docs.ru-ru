---
title: Метод IMetaDataImport::EnumMemberRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
ms.openlocfilehash: 743b6bed1a5d62f5214b8366b1a3c6e4ebecb98b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441719"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="f1481-102">Метод IMetaDataImport::EnumMemberRefs</span><span class="sxs-lookup"><span data-stu-id="f1481-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="f1481-103">Перечисляет токены MemberRef, представляющие члены указанного типа.</span><span class="sxs-lookup"><span data-stu-id="f1481-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1481-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1481-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1481-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1481-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f1481-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="f1481-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="f1481-107">окне Токен TypeDef, TypeRef, MethodDef или ModuleRef для типа, элементы которого необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="f1481-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="f1481-108">заполняет Массив, используемый для хранения токенов MemberRef.</span><span class="sxs-lookup"><span data-stu-id="f1481-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f1481-109">[in] Максимальный размер массива `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="f1481-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f1481-110">заполняет Фактическое число токенов MemberRef, возвращаемых в `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="f1481-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1481-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f1481-111">Return Value</span></span>  
  
|<span data-ttu-id="f1481-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1481-112">HRESULT</span></span>|<span data-ttu-id="f1481-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f1481-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f1481-114">`EnumMemberRefs` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f1481-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f1481-115">Отсутствуют токены MemberRef для перечисления.</span><span class="sxs-lookup"><span data-stu-id="f1481-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="f1481-116">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="f1481-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1481-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f1481-117">Requirements</span></span>  
 <span data-ttu-id="f1481-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1481-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1481-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f1481-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1481-120">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f1481-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1481-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1481-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1481-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f1481-122">See also</span></span>

- [<span data-ttu-id="f1481-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f1481-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f1481-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f1481-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
