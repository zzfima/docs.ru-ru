---
title: Метод IMetaDataAssemblyImport::EnumExportedTypes
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: f00fe5bce2f808265add228406dfaa2ccc267545
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176010"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="321a1-102">Метод IMetaDataAssemblyImport::EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="321a1-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="321a1-103">Перечисляет экспортированные типы, упомянутые в сборке в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="321a1-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="321a1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="321a1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="321a1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="321a1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="321a1-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="321a1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="321a1-107">Это должно быть нулевая величина, `EnumExportedTypes` когда метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="321a1-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="321a1-108">(ваут) Перечисление `mdExportedType` токенов метаданных.</span><span class="sxs-lookup"><span data-stu-id="321a1-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="321a1-109">(в) Максимальное количество `mdExportedType` токенов, которые могут `rExportedTypes` быть размещены в массиве.</span><span class="sxs-lookup"><span data-stu-id="321a1-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="321a1-110">(ваут) Количество `mdExportedType` токенов фактически помещено в `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="321a1-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="321a1-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="321a1-111">Return Value</span></span>  
  
|<span data-ttu-id="321a1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="321a1-112">HRESULT</span></span>|<span data-ttu-id="321a1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="321a1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="321a1-114">`EnumExportedTypes`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="321a1-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="321a1-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="321a1-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="321a1-116">В этом `pcTokens` случае, устанавливается до нуля.</span><span class="sxs-lookup"><span data-stu-id="321a1-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="321a1-117">Требования</span><span class="sxs-lookup"><span data-stu-id="321a1-117">Requirements</span></span>  
 <span data-ttu-id="321a1-118">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="321a1-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="321a1-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="321a1-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="321a1-120">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="321a1-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="321a1-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="321a1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="321a1-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="321a1-122">See also</span></span>

- [<span data-ttu-id="321a1-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="321a1-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
