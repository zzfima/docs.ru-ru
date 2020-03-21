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
ms.openlocfilehash: e628cf5dab8006b0df0ab6c60dc995cd0c6bb29d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175451"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="b5343-102">Метод IMetaDataImport::EnumPermissionSets</span><span class="sxs-lookup"><span data-stu-id="b5343-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="b5343-103">Перечисляет разрешения для объектов в указанной области метаданных.</span><span class="sxs-lookup"><span data-stu-id="b5343-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5343-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5343-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5343-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5343-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b5343-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="b5343-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b5343-107">Это должно быть NULL для первого вызова этого метода.</span><span class="sxs-lookup"><span data-stu-id="b5343-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="b5343-108">(в) Токен метаданных, ограничивающий область поиска, или NULL для поиска максимально возможного объема.</span><span class="sxs-lookup"><span data-stu-id="b5343-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="b5343-109">(в) Флаги, <xref:System.Security.Permissions.SecurityAction> представляющие значения `rPermission`для включения в , или ноль, чтобы вернуть все действия.</span><span class="sxs-lookup"><span data-stu-id="b5343-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="b5343-110">(ваут) Массив, используемый для хранения токенов Разрешения.</span><span class="sxs-lookup"><span data-stu-id="b5343-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b5343-111">[in] Максимальный размер массива `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="b5343-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b5343-112">(ваут) Число токенов Разрешения, `rPermission`возвращенных в .</span><span class="sxs-lookup"><span data-stu-id="b5343-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5343-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b5343-113">Return Value</span></span>  
  
|<span data-ttu-id="b5343-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5343-114">HRESULT</span></span>|<span data-ttu-id="b5343-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b5343-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b5343-116">`EnumPermissionSets`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="b5343-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b5343-117">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="b5343-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="b5343-118">В этом `pcTokens` случае, равна нулю.</span><span class="sxs-lookup"><span data-stu-id="b5343-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5343-119">Требования</span><span class="sxs-lookup"><span data-stu-id="b5343-119">Requirements</span></span>  
 <span data-ttu-id="b5343-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5343-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5343-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b5343-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5343-122">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5343-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5343-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5343-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5343-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b5343-124">See also</span></span>

- [<span data-ttu-id="b5343-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b5343-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b5343-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b5343-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
