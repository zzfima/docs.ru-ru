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
ms.openlocfilehash: 0b7ca6f9878ed2fa2d90ea93e5101f0a66ec2d5e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440204"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="293d6-102">Метод IMetaDataAssemblyEmit::DefineFile</span><span class="sxs-lookup"><span data-stu-id="293d6-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="293d6-103">Создает структуру метаданных `File`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="293d6-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="293d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="293d6-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="293d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="293d6-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="293d6-106">окне Имя файла, который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="293d6-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="293d6-107">окне Указатель на хэш-данные, связанные со сборкой.</span><span class="sxs-lookup"><span data-stu-id="293d6-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="293d6-108">окне Размер в байтах `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="293d6-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="293d6-109">окне Побитовое сочетание значений `FileFlags`, определяющих настройки свойств.</span><span class="sxs-lookup"><span data-stu-id="293d6-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="293d6-110">заполняет Указатель на возвращаемый маркер `File`.</span><span class="sxs-lookup"><span data-stu-id="293d6-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="293d6-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="293d6-111">Remarks</span></span>  
 <span data-ttu-id="293d6-112">Одна `File` структура метаданных должна быть определена для каждого файла, который был частью этой сборки на момент построения этой сборки, за исключением файла, содержащего метаданные.</span><span class="sxs-lookup"><span data-stu-id="293d6-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="293d6-113">Требования</span><span class="sxs-lookup"><span data-stu-id="293d6-113">Requirements</span></span>  
 <span data-ttu-id="293d6-114">**Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="293d6-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="293d6-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="293d6-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="293d6-116">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="293d6-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="293d6-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="293d6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="293d6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="293d6-118">See also</span></span>

- [<span data-ttu-id="293d6-119">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="293d6-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
