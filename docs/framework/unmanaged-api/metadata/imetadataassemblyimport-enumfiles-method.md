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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1995ed0b281978b45b01dbeda54b02094a30412
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445743"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="11a34-102">Метод IMetaDataAssemblyImport::EnumFiles</span><span class="sxs-lookup"><span data-stu-id="11a34-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="11a34-103">Перечисляет файлы, на которые ссылается манифест текущей сборки.</span><span class="sxs-lookup"><span data-stu-id="11a34-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11a34-104">Syntax</span></span>  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11a34-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11a34-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="11a34-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="11a34-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="11a34-107">Это должно быть значение null при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="11a34-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="11a34-108">[out] Массив, используемый для хранения `mdFile` токены метаданных.</span><span class="sxs-lookup"><span data-stu-id="11a34-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="11a34-109">[in] Максимальное число `mdFile` маркеры, которые могут быть помещены в `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="11a34-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="11a34-110">[out] Число `mdFile` токены непосредственно в `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="11a34-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11a34-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="11a34-111">Return Value</span></span>  
  
|<span data-ttu-id="11a34-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11a34-112">HRESULT</span></span>|<span data-ttu-id="11a34-113">Описание</span><span class="sxs-lookup"><span data-stu-id="11a34-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="11a34-114">`EnumFiles` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="11a34-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="11a34-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="11a34-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="11a34-116">В этом случае `pcTokens` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="11a34-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11a34-117">Требования</span><span class="sxs-lookup"><span data-stu-id="11a34-117">Requirements</span></span>  
 <span data-ttu-id="11a34-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11a34-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a34-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="11a34-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11a34-120">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11a34-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11a34-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a34-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a34-122">См. также</span><span class="sxs-lookup"><span data-stu-id="11a34-122">See Also</span></span>  
 [<span data-ttu-id="11a34-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="11a34-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
