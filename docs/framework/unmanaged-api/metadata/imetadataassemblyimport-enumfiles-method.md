---
title: Метод IMetaDataAssemblyImport::EnumFiles
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: e4549789ea1af584c0850a535d9f6bb54f844ce0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443543"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="6f5f3-102">Метод IMetaDataAssemblyImport::EnumFiles</span><span class="sxs-lookup"><span data-stu-id="6f5f3-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="6f5f3-103">Перечисляет файлы, на которые ссылается текущий манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="6f5f3-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f5f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f5f3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f5f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f5f3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6f5f3-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="6f5f3-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6f5f3-107">При первом вызове этого метода это значение должно быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="6f5f3-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="6f5f3-108">заполняет Массив, используемый для хранения маркеров метаданных `mdFile`.</span><span class="sxs-lookup"><span data-stu-id="6f5f3-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6f5f3-109">окне Максимальное число маркеров `mdFile`, которые могут быть помещены в `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="6f5f3-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6f5f3-110">заполняет Число маркеров `mdFile`, фактически помещаемых в `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="6f5f3-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f5f3-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6f5f3-111">Return Value</span></span>  
  
|<span data-ttu-id="6f5f3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f5f3-112">HRESULT</span></span>|<span data-ttu-id="6f5f3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6f5f3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6f5f3-114">`EnumFiles` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="6f5f3-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6f5f3-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="6f5f3-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="6f5f3-116">В этом случае `pcTokens` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="6f5f3-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f5f3-117">Требования</span><span class="sxs-lookup"><span data-stu-id="6f5f3-117">Requirements</span></span>  
 <span data-ttu-id="6f5f3-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f5f3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f5f3-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="6f5f3-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6f5f3-120">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6f5f3-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6f5f3-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f5f3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5f3-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f5f3-122">See also</span></span>

- [<span data-ttu-id="6f5f3-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="6f5f3-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
