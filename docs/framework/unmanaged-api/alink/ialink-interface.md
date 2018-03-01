---
title: "Интерфейс IALink"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IALink
helpviewer_keywords:
- IALink interface
ms.assetid: 50abd02d-6488-4815-999b-4fb89af4d568
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4c58c3aa5ca1ec2d8b3bc820b2b7a500604b4b7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ialink-interface"></a><span data-ttu-id="ddaec-102">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="ddaec-102">IALink Interface</span></span>
<span data-ttu-id="ddaec-103">Помогает при конструировании сборок платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ddaec-103">Helps in constructing .NET Framework assemblies.</span></span> <span data-ttu-id="ddaec-104">Помимо прочего интерфейс содержит методы, которые помогают в написании манифеста многомодульных сборок, подписывание сборок со строгими именами и создании модулей NETMODULE.</span><span class="sxs-lookup"><span data-stu-id="ddaec-104">Among other things, the interface contains methods that assist in writing assembly manifests for multi-module assemblies, signing assemblies with strong names, and creating netmodules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ddaec-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ddaec-105">In This Section</span></span>  
 [<span data-ttu-id="ddaec-106">Метод1 AddFile</span><span class="sxs-lookup"><span data-stu-id="ddaec-106">AddFile Method1</span></span>](../../../../docs/framework/unmanaged-api/alink/addfile-method.md)  
  
 [<span data-ttu-id="ddaec-107">Метод1 AddImport</span><span class="sxs-lookup"><span data-stu-id="ddaec-107">AddImport Method1</span></span>](../../../../docs/framework/unmanaged-api/alink/addimport-method.md)  
  
 [<span data-ttu-id="ddaec-108">Метод CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="ddaec-108">CloseAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/alink/closeassembly-method.md)  
  
 [<span data-ttu-id="ddaec-109">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="ddaec-109">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/alink/closeenum-method.md)  
  
 [<span data-ttu-id="ddaec-110">Метод EmbedResource</span><span class="sxs-lookup"><span data-stu-id="ddaec-110">EmbedResource Method</span></span>](../../../../docs/framework/unmanaged-api/alink/embedresource-method.md)  
  
 [<span data-ttu-id="ddaec-111">Метод EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="ddaec-111">EmitAssemblyCustomAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/alink/emitassemblycustomattribute-method.md)  
  
 [<span data-ttu-id="ddaec-112">Метод EmitManifest</span><span class="sxs-lookup"><span data-stu-id="ddaec-112">EmitManifest Method</span></span>](../../../../docs/framework/unmanaged-api/alink/emitmanifest-method.md)  
  
 [<span data-ttu-id="ddaec-113">Метод EndMerge</span><span class="sxs-lookup"><span data-stu-id="ddaec-113">EndMerge Method</span></span>](../../../../docs/framework/unmanaged-api/alink/endmerge-method.md)  
  
 [<span data-ttu-id="ddaec-114">Метод EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="ddaec-114">EnumCustomAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/alink/enumcustomattributes-method.md)  
  
 [<span data-ttu-id="ddaec-115">Метод EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="ddaec-115">EnumImportTypes Method</span></span>](../../../../docs/framework/unmanaged-api/alink/enumimporttypes-method.md)  
  
 [<span data-ttu-id="ddaec-116">Метод ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="ddaec-116">ExportNestedType Method</span></span>](../../../../docs/framework/unmanaged-api/alink/exportnestedtype-method.md)  
  
 [<span data-ttu-id="ddaec-117">Метод ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="ddaec-117">ExportNestedTypeForwarder Method</span></span>](../../../../docs/framework/unmanaged-api/alink/exportnestedtypeforwarder-method.md)  
  
 [<span data-ttu-id="ddaec-118">Метод ExportType</span><span class="sxs-lookup"><span data-stu-id="ddaec-118">ExportType Method</span></span>](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md)  
  
 [<span data-ttu-id="ddaec-119">Метод ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="ddaec-119">ExportTypeForwarder Method</span></span>](../../../../docs/framework/unmanaged-api/alink/exporttypeforwarder-method.md)  
  
 [<span data-ttu-id="ddaec-120">Метод FreeWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="ddaec-120">FreeWin32ResBlob Method</span></span>](../../../../docs/framework/unmanaged-api/alink/freewin32resblob-method.md)  
  
 [<span data-ttu-id="ddaec-121">Метод GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="ddaec-121">GetAssemblyRefHash Method</span></span>](../../../../docs/framework/unmanaged-api/alink/getassemblyrefhash-method.md)  
  
 [<span data-ttu-id="ddaec-122">Метод GetResolutionScope</span><span class="sxs-lookup"><span data-stu-id="ddaec-122">GetResolutionScope Method</span></span>](../../../../docs/framework/unmanaged-api/alink/getresolutionscope-method.md)  
  
 [<span data-ttu-id="ddaec-123">Метод1 GetScope</span><span class="sxs-lookup"><span data-stu-id="ddaec-123">GetScope Method1</span></span>](../../../../docs/framework/unmanaged-api/alink/getscope-method.md)  
  
 [<span data-ttu-id="ddaec-124">Метод GetWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="ddaec-124">GetWin32ResBlob Method</span></span>](../../../../docs/framework/unmanaged-api/alink/getwin32resblob-method.md)  
  
 [<span data-ttu-id="ddaec-125">Метод ImportFile</span><span class="sxs-lookup"><span data-stu-id="ddaec-125">ImportFile Method</span></span>](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)  
  
 [<span data-ttu-id="ddaec-126">Метод ImportFile2</span><span class="sxs-lookup"><span data-stu-id="ddaec-126">ImportFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/alink/importfile2-method.md)  
  
 [<span data-ttu-id="ddaec-127">Метод ImportTypes</span><span class="sxs-lookup"><span data-stu-id="ddaec-127">ImportTypes Method</span></span>](../../../../docs/framework/unmanaged-api/alink/importtypes-method.md)  
  
 <span data-ttu-id="ddaec-128">«Метод Init»</span><span class="sxs-lookup"><span data-stu-id="ddaec-128">"Init Method"</span></span>  
  
 [<span data-ttu-id="ddaec-129">Метод LinkResource</span><span class="sxs-lookup"><span data-stu-id="ddaec-129">LinkResource Method</span></span>](../../../../docs/framework/unmanaged-api/alink/linkresource-method.md)  
  
 [<span data-ttu-id="ddaec-130">Метод PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="ddaec-130">PreCloseAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/alink/precloseassembly-method.md)  
  
 [<span data-ttu-id="ddaec-131">Метод SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="ddaec-131">SetAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/alink/setassemblyfile-method.md)  
  
 [<span data-ttu-id="ddaec-132">Метод SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="ddaec-132">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/alink/setassemblyprops-method.md)  
  
 [<span data-ttu-id="ddaec-133">Метод SetNonAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="ddaec-133">SetNonAssemblyFlags Method</span></span>](../../../../docs/framework/unmanaged-api/alink/setnonassemblyflags-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="ddaec-134">См. также</span><span class="sxs-lookup"><span data-stu-id="ddaec-134">See Also</span></span>  
 [<span data-ttu-id="ddaec-135">API ALink</span><span class="sxs-lookup"><span data-stu-id="ddaec-135">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [<span data-ttu-id="ddaec-136">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="ddaec-136">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ddaec-137">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="ddaec-137">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
