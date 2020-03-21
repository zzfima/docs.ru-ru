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
ms.openlocfilehash: 70f76318f51047cb81262f744a6fbed5fe401692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177816"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="bf67f-102">Метод IMetaDataAssemblyImport::EnumFiles</span><span class="sxs-lookup"><span data-stu-id="bf67f-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="bf67f-103">Перечисляет файлы, упомянутые в текущем манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="bf67f-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf67f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf67f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf67f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf67f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bf67f-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="bf67f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="bf67f-107">Это должно быть нулевая стоимость для первого вызова этого метода.</span><span class="sxs-lookup"><span data-stu-id="bf67f-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="bf67f-108">(ваут) Массив, используемый `mdFile` для хранения токенов метаданных.</span><span class="sxs-lookup"><span data-stu-id="bf67f-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bf67f-109">(в) Максимальное количество `mdFile` токенов, которые `rFiles`могут быть размещены в .</span><span class="sxs-lookup"><span data-stu-id="bf67f-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="bf67f-110">(ваут) Количество `mdFile` токенов фактически помещено в `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="bf67f-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf67f-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bf67f-111">Return Value</span></span>  
  
|<span data-ttu-id="bf67f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bf67f-112">HRESULT</span></span>|<span data-ttu-id="bf67f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bf67f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bf67f-114">`EnumFiles`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="bf67f-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bf67f-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="bf67f-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="bf67f-116">В этом `pcTokens` случае, устанавливается до нуля.</span><span class="sxs-lookup"><span data-stu-id="bf67f-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf67f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="bf67f-117">Requirements</span></span>  
 <span data-ttu-id="bf67f-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf67f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf67f-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bf67f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf67f-120">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf67f-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf67f-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf67f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf67f-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bf67f-122">See also</span></span>

- [<span data-ttu-id="bf67f-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="bf67f-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
