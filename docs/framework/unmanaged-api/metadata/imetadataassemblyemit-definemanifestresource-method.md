---
title: "Метод IMetaDataAssemblyEmit::DefineManifestResource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineManifestResource
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 516099f0735e83982fcbab62936bb398c4f7b02d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="90f75-102">Метод IMetaDataAssemblyEmit::DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="90f75-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="90f75-103">Создает структуру `ManifestResource`, содержащую метаданные для указанного ресурса манифеста, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="90f75-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90f75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90f75-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90f75-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="90f75-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="90f75-106">[in] Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="90f75-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="90f75-107">[in] Токен метаданных типа `mdtFile` или `mdtAssemblyRef` , сопоставляемый поставщика ресурсов.</span><span class="sxs-lookup"><span data-stu-id="90f75-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="90f75-108">Значение NULL указывает на то, что файл внедренные метаданные поставщика ресурсов.</span><span class="sxs-lookup"><span data-stu-id="90f75-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="90f75-109">[in] Смещение в начало ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="90f75-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="90f75-110">Для ресурсов в отдельных файлах это всегда будет равно нулю.</span><span class="sxs-lookup"><span data-stu-id="90f75-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="90f75-111">Если ресурс внедрен в PE-файл (переносимый исполняемый файл), это смещение большого двоичного ОБЪЕКТА, который начинается в расположении, указанном в файле заголовка cor.h ресурса.</span><span class="sxs-lookup"><span data-stu-id="90f75-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="90f75-112">[in] Побитовая комбинация значений флага, которые определяют параметры свойств для определения ресурса.</span><span class="sxs-lookup"><span data-stu-id="90f75-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="90f75-113">[out] Указатель на токен возвращенные метаданные.</span><span class="sxs-lookup"><span data-stu-id="90f75-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90f75-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="90f75-114">Remarks</span></span>  
 <span data-ttu-id="90f75-115">Один `ManifestResource` структуру метаданных должны быть определены для каждого ресурса, который реализован в каждом из файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="90f75-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90f75-116">Требования</span><span class="sxs-lookup"><span data-stu-id="90f75-116">Requirements</span></span>  
 <span data-ttu-id="90f75-117">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90f75-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90f75-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90f75-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90f75-119">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="90f75-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90f75-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90f75-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90f75-121">См. также</span><span class="sxs-lookup"><span data-stu-id="90f75-121">See Also</span></span>  
 [<span data-ttu-id="90f75-122">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="90f75-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
