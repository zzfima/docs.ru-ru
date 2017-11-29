---
title: "Метод IMetaDataImport::EnumPermissionSets"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumPermissionSets
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 031e97ad1b8180a64bc789ae52e141932d600782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="ee12b-102">Метод IMetaDataImport::EnumPermissionSets</span><span class="sxs-lookup"><span data-stu-id="ee12b-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="ee12b-103">Перечисляет разрешения для объектов в указанной области метаданных.</span><span class="sxs-lookup"><span data-stu-id="ee12b-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee12b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee12b-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ee12b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee12b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ee12b-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="ee12b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ee12b-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="ee12b-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="ee12b-108">[in] Токен метаданных, который ограничивает область поиска, или значение NULL для поиска возможных широкой области.</span><span class="sxs-lookup"><span data-stu-id="ee12b-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="ee12b-109">[in] Флаги представляющий <xref:System.Security.Permissions.SecurityAction> значений для включения в `rPermission`, или ноль для возвращения всех действий.</span><span class="sxs-lookup"><span data-stu-id="ee12b-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="ee12b-110">[out] Массив, используемый для хранения токенов разрешение.</span><span class="sxs-lookup"><span data-stu-id="ee12b-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ee12b-111">[in] Максимальный размер массива `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="ee12b-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ee12b-112">[out] Число маркеров разрешение, возвращаемых в `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="ee12b-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee12b-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ee12b-113">Return Value</span></span>  
  
|<span data-ttu-id="ee12b-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee12b-114">HRESULT</span></span>|<span data-ttu-id="ee12b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ee12b-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ee12b-116">`EnumPermissionSets`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ee12b-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ee12b-117">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="ee12b-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="ee12b-118">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="ee12b-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee12b-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ee12b-119">Requirements</span></span>  
 <span data-ttu-id="ee12b-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee12b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee12b-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee12b-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee12b-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee12b-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee12b-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee12b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee12b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ee12b-124">See Also</span></span>  
 [<span data-ttu-id="ee12b-125">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ee12b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ee12b-126">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ee12b-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
