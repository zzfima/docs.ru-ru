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
ms.openlocfilehash: 9d0f443b5b7d2d358534e888c3fc84ad3f554119
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450048"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="a6b81-102">Метод IMetaDataImport::EnumPermissionSets</span><span class="sxs-lookup"><span data-stu-id="a6b81-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="a6b81-103">Перечисляет разрешения для объектов в указанной области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a6b81-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6b81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6b81-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a6b81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6b81-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a6b81-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="a6b81-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a6b81-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="a6b81-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="a6b81-108">окне Токен метаданных, ограничивающий область поиска, или значение NULL для поиска по самой широкой области.</span><span class="sxs-lookup"><span data-stu-id="a6b81-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="a6b81-109">окне Флаги, представляющие <xref:System.Security.Permissions.SecurityAction> значения, включаемые в `rPermission`, или ноль для возврата всех действий.</span><span class="sxs-lookup"><span data-stu-id="a6b81-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="a6b81-110">заполняет Массив, используемый для хранения маркеров разрешений.</span><span class="sxs-lookup"><span data-stu-id="a6b81-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a6b81-111">[in] Максимальный размер массива `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="a6b81-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a6b81-112">заполняет Число маркеров разрешений, возвращаемых в `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="a6b81-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6b81-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a6b81-113">Return Value</span></span>  
  
|<span data-ttu-id="a6b81-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6b81-114">HRESULT</span></span>|<span data-ttu-id="a6b81-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a6b81-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a6b81-116">`EnumPermissionSets` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="a6b81-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a6b81-117">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="a6b81-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="a6b81-118">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="a6b81-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6b81-119">Требования</span><span class="sxs-lookup"><span data-stu-id="a6b81-119">Requirements</span></span>  
 <span data-ttu-id="a6b81-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6b81-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6b81-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a6b81-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6b81-122">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a6b81-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6b81-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6b81-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b81-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a6b81-124">See also</span></span>

- [<span data-ttu-id="a6b81-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a6b81-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a6b81-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a6b81-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
