---
title: "Метод IMetaDataImport2::GetPEKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetPEKind
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9fc963f38a845db67bb5b5d377ecabf9a40c359f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="35214-102">Метод IMetaDataImport2::GetPEKind</span><span class="sxs-lookup"><span data-stu-id="35214-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="35214-103">Возвращает значение, идентифицирующее характер кода в переносимом исполняемом (PE) файла, обычно файл EXE или DLL, которая определена в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="35214-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35214-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35214-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35214-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="35214-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="35214-106">[out] Указатель на значение [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) перечисление, описывающее PE-файла.</span><span class="sxs-lookup"><span data-stu-id="35214-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="35214-107">[out] Указатель на значение, которое определяет архитектуру компьютера.</span><span class="sxs-lookup"><span data-stu-id="35214-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="35214-108">В следующем разделе для возможных значений.</span><span class="sxs-lookup"><span data-stu-id="35214-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35214-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="35214-109">Remarks</span></span>  
 <span data-ttu-id="35214-110">Значения, упоминаемого по `pdwMachine` параметр может принимать одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="35214-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="35214-111">Значение</span><span class="sxs-lookup"><span data-stu-id="35214-111">Value</span></span>|<span data-ttu-id="35214-112">Архитектура компьютера</span><span class="sxs-lookup"><span data-stu-id="35214-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="35214-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="35214-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="35214-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="35214-114">0x014C</span></span>|<span data-ttu-id="35214-115">x86</span><span class="sxs-lookup"><span data-stu-id="35214-115">x86</span></span>|  
|<span data-ttu-id="35214-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="35214-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="35214-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="35214-117">0x0200</span></span>|<span data-ttu-id="35214-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="35214-118">Intel IPF</span></span>|  
|<span data-ttu-id="35214-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="35214-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="35214-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="35214-120">0x8664</span></span>|<span data-ttu-id="35214-121">x64</span><span class="sxs-lookup"><span data-stu-id="35214-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35214-122">Требования</span><span class="sxs-lookup"><span data-stu-id="35214-122">Requirements</span></span>  
 <span data-ttu-id="35214-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35214-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35214-124">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35214-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35214-125">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35214-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35214-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35214-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35214-127">См. также</span><span class="sxs-lookup"><span data-stu-id="35214-127">See Also</span></span>  
 [<span data-ttu-id="35214-128">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="35214-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="35214-129">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="35214-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="35214-130">Перечисление CorPEKind</span><span class="sxs-lookup"><span data-stu-id="35214-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
