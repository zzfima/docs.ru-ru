---
title: Интерфейс IALink
ms.date: 03/30/2017
f1_keywords:
- IALink
helpviewer_keywords:
- IALink interface
ms.assetid: 50abd02d-6488-4815-999b-4fb89af4d568
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7324ddb63f000f55a16c4963c808f658aa9098a7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787327"
---
# <a name="ialink-interface"></a><span data-ttu-id="83eff-102">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="83eff-102">IALink Interface</span></span>
<span data-ttu-id="83eff-103">Помогает при построении сборок .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83eff-103">Helps in constructing .NET Framework assemblies.</span></span> <span data-ttu-id="83eff-104">Помимо прочего, интерфейс содержит методы, которые помогают в написании манифестов сборок для многомодульных сборок, подписи сборок со строгими именами и создания модулей NETMODULE.</span><span class="sxs-lookup"><span data-stu-id="83eff-104">Among other things, the interface contains methods that assist in writing assembly manifests for multi-module assemblies, signing assemblies with strong names, and creating netmodules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83eff-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="83eff-105">In This Section</span></span>  
 [<span data-ttu-id="83eff-106">Метод AddFile</span><span class="sxs-lookup"><span data-stu-id="83eff-106">AddFile Method</span></span>](addfile-method.md)  
  
 [<span data-ttu-id="83eff-107">Метод AddImport</span><span class="sxs-lookup"><span data-stu-id="83eff-107">AddImport Method</span></span>](addimport-method.md)  
  
 [<span data-ttu-id="83eff-108">Метод CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="83eff-108">CloseAssembly Method</span></span>](closeassembly-method.md)  
  
 [<span data-ttu-id="83eff-109">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="83eff-109">CloseEnum Method</span></span>](closeenum-method.md)  
  
 [<span data-ttu-id="83eff-110">Метод EmbedResource</span><span class="sxs-lookup"><span data-stu-id="83eff-110">EmbedResource Method</span></span>](embedresource-method.md)  
  
 [<span data-ttu-id="83eff-111">Метод EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="83eff-111">EmitAssemblyCustomAttribute Method</span></span>](emitassemblycustomattribute-method.md)  
  
 [<span data-ttu-id="83eff-112">Метод EmitManifest</span><span class="sxs-lookup"><span data-stu-id="83eff-112">EmitManifest Method</span></span>](emitmanifest-method.md)  
  
 [<span data-ttu-id="83eff-113">Метод EndMerge</span><span class="sxs-lookup"><span data-stu-id="83eff-113">EndMerge Method</span></span>](endmerge-method.md)  
  
 [<span data-ttu-id="83eff-114">Метод EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="83eff-114">EnumCustomAttributes Method</span></span>](enumcustomattributes-method.md)  
  
 [<span data-ttu-id="83eff-115">Метод EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="83eff-115">EnumImportTypes Method</span></span>](enumimporttypes-method.md)  
  
 [<span data-ttu-id="83eff-116">Метод ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="83eff-116">ExportNestedType Method</span></span>](exportnestedtype-method.md)  
  
 [<span data-ttu-id="83eff-117">Метод ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="83eff-117">ExportNestedTypeForwarder Method</span></span>](exportnestedtypeforwarder-method.md)  
  
 [<span data-ttu-id="83eff-118">Метод ExportType</span><span class="sxs-lookup"><span data-stu-id="83eff-118">ExportType Method</span></span>](exporttype-method.md)  
  
 [<span data-ttu-id="83eff-119">Метод ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="83eff-119">ExportTypeForwarder Method</span></span>](exporttypeforwarder-method.md)  
  
 [<span data-ttu-id="83eff-120">Метод FreeWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="83eff-120">FreeWin32ResBlob Method</span></span>](freewin32resblob-method.md)  
  
 [<span data-ttu-id="83eff-121">Метод GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="83eff-121">GetAssemblyRefHash Method</span></span>](getassemblyrefhash-method.md)  
  
 [<span data-ttu-id="83eff-122">Метод GetResolutionScope</span><span class="sxs-lookup"><span data-stu-id="83eff-122">GetResolutionScope Method</span></span>](getresolutionscope-method.md)  
  
 [<span data-ttu-id="83eff-123">Метод superscope</span><span class="sxs-lookup"><span data-stu-id="83eff-123">GetScope Method</span></span>](getscope-method.md)  
  
 [<span data-ttu-id="83eff-124">Метод GetWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="83eff-124">GetWin32ResBlob Method</span></span>](getwin32resblob-method.md)  
  
 [<span data-ttu-id="83eff-125">Метод ImportFile</span><span class="sxs-lookup"><span data-stu-id="83eff-125">ImportFile Method</span></span>](importfile-method.md)  
  
 [<span data-ttu-id="83eff-126">Метод ImportFile2</span><span class="sxs-lookup"><span data-stu-id="83eff-126">ImportFile2 Method</span></span>](importfile2-method.md)  
  
 [<span data-ttu-id="83eff-127">Метод ImportTypes</span><span class="sxs-lookup"><span data-stu-id="83eff-127">ImportTypes Method</span></span>](importtypes-method.md)  
  
 <span data-ttu-id="83eff-128">"Метод Init"</span><span class="sxs-lookup"><span data-stu-id="83eff-128">"Init Method"</span></span>  
  
 [<span data-ttu-id="83eff-129">Метод LinkResource</span><span class="sxs-lookup"><span data-stu-id="83eff-129">LinkResource Method</span></span>](linkresource-method.md)  
  
 [<span data-ttu-id="83eff-130">Метод PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="83eff-130">PreCloseAssembly Method</span></span>](precloseassembly-method.md)  
  
 [<span data-ttu-id="83eff-131">Метод SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="83eff-131">SetAssemblyFile Method</span></span>](setassemblyfile-method.md)  
  
 [<span data-ttu-id="83eff-132">Метод SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="83eff-132">SetAssemblyProps Method</span></span>](setassemblyprops-method.md)  
  
 [<span data-ttu-id="83eff-133">Метод SetNonAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="83eff-133">SetNonAssemblyFlags Method</span></span>](setnonassemblyflags-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="83eff-134">См. также</span><span class="sxs-lookup"><span data-stu-id="83eff-134">See also</span></span>

- [<span data-ttu-id="83eff-135">API ALink</span><span class="sxs-lookup"><span data-stu-id="83eff-135">ALink API</span></span>](index.md)
- [<span data-ttu-id="83eff-136">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="83eff-136">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="83eff-137">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="83eff-137">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
