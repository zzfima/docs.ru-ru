---
title: Метод IMetaDataAssemblyEmit::DefineFile
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: cabd6a47e5d6fc2a4cea87b16d349d9c778b3507
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176062"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="11fc3-102">Метод IMetaDataAssemblyEmit::DefineFile</span><span class="sxs-lookup"><span data-stu-id="11fc3-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="11fc3-103">Создает структуру метаданных `File`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="11fc3-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11fc3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11fc3-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11fc3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11fc3-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="11fc3-106">(в) Имя файла, который будет употребляться.</span><span class="sxs-lookup"><span data-stu-id="11fc3-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="11fc3-107">(в) Указатель на хэш-данные, связанные с сборкой.</span><span class="sxs-lookup"><span data-stu-id="11fc3-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="11fc3-108">(в) Размер байтов `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="11fc3-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="11fc3-109">(в) Битовая комбинация значений, `FileFlags` определяющих параметры свойств.</span><span class="sxs-lookup"><span data-stu-id="11fc3-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="11fc3-110">(ваут) Указатель на возвращенный `File` токен.</span><span class="sxs-lookup"><span data-stu-id="11fc3-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11fc3-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="11fc3-111">Remarks</span></span>  
 <span data-ttu-id="11fc3-112">Для `File` каждого файла, который был частью этой сборки на момент построения сборки, должна быть определена одна структура метаданных, за исключением файла, содержащего метаданные.</span><span class="sxs-lookup"><span data-stu-id="11fc3-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11fc3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="11fc3-113">Requirements</span></span>  
 <span data-ttu-id="11fc3-114">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11fc3-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11fc3-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="11fc3-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11fc3-116">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11fc3-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11fc3-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11fc3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11fc3-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="11fc3-118">See also</span></span>

- [<span data-ttu-id="11fc3-119">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="11fc3-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
