---
title: Метод IMetaDataImport::EnumPermissionSets
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28e6ad309af808638400fc27255acdee381b4c6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992320"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="ea0c1-102">Метод IMetaDataImport::EnumPermissionSets</span><span class="sxs-lookup"><span data-stu-id="ea0c1-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="ea0c1-103">Перечисляет разрешения для объектов в указанной области метаданных.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea0c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea0c1-104">Syntax</span></span>  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea0c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea0c1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ea0c1-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ea0c1-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="ea0c1-108">[in] Токен метаданных, который ограничивает область поиска, или значение NULL, для поиска возможных широкой области.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="ea0c1-109">[in] Флаги, представляющие <xref:System.Security.Permissions.SecurityAction> значений для включения в `rPermission`, или ноль для возвращения всех действий.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="ea0c1-110">[out] Массив, используемый для хранения токенов разрешение.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ea0c1-111">[in] Максимальный размер массива `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ea0c1-112">[out] Число маркеров разрешения, возвращаемые в `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea0c1-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ea0c1-113">Return Value</span></span>  
  
|<span data-ttu-id="ea0c1-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea0c1-114">HRESULT</span></span>|<span data-ttu-id="ea0c1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ea0c1-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ea0c1-116">`EnumPermissionSets` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ea0c1-117">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="ea0c1-118">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="ea0c1-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea0c1-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ea0c1-119">Requirements</span></span>  
 <span data-ttu-id="ea0c1-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea0c1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea0c1-121">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea0c1-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea0c1-122">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea0c1-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea0c1-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea0c1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea0c1-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ea0c1-124">See also</span></span>

- [<span data-ttu-id="ea0c1-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ea0c1-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ea0c1-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ea0c1-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
