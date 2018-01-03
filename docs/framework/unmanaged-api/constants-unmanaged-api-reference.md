---
title: "Константы (справочные сведения о неуправляемых API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e086e856bb7a872b14815825f78d208ff5296899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="cc69c-102">Константы (справочные сведения о неуправляемых API)</span><span class="sxs-lookup"><span data-stu-id="cc69c-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="cc69c-103">В этом разделе описывается тип языка, поставщика языка и константы типа документа, которые определены в файле CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="cc69c-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="cc69c-104">Константы типа языка</span><span class="sxs-lookup"><span data-stu-id="cc69c-104">Language Type Constants</span></span>  
 <span data-ttu-id="cc69c-105">Следующая таблица показывает языка тип константы, которые представляют идентификаторы GUID, обозначающие языки программирования.</span><span class="sxs-lookup"><span data-stu-id="cc69c-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="cc69c-106">Символ</span><span class="sxs-lookup"><span data-stu-id="cc69c-106">Symbol</span></span>|<span data-ttu-id="cc69c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cc69c-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cc69c-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="cc69c-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="cc69c-109">Указывает язык C.</span><span class="sxs-lookup"><span data-stu-id="cc69c-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="cc69c-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="cc69c-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="cc69c-111">Указывает язык C++.</span><span class="sxs-lookup"><span data-stu-id="cc69c-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="cc69c-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="cc69c-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="cc69c-113">Указывает язык C#.</span><span class="sxs-lookup"><span data-stu-id="cc69c-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="cc69c-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="cc69c-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="cc69c-115">Указывает основной язык.</span><span class="sxs-lookup"><span data-stu-id="cc69c-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="cc69c-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="cc69c-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="cc69c-117">Указывает язык Java.</span><span class="sxs-lookup"><span data-stu-id="cc69c-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="cc69c-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="cc69c-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="cc69c-119">Указывает язык COBOL.</span><span class="sxs-lookup"><span data-stu-id="cc69c-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="cc69c-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="cc69c-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="cc69c-121">Указывает языка Pascal.</span><span class="sxs-lookup"><span data-stu-id="cc69c-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="cc69c-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="cc69c-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="cc69c-123">Указывает код сборки Microsoft промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="cc69c-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="cc69c-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="cc69c-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="cc69c-125">Указывает язык JScript.</span><span class="sxs-lookup"><span data-stu-id="cc69c-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="cc69c-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="cc69c-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="cc69c-127">Обозначает язык SMC.</span><span class="sxs-lookup"><span data-stu-id="cc69c-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="cc69c-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="cc69c-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="cc69c-129">Указывает язык C++ включена для платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cc69c-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="cc69c-130">Константы поставщиков языков</span><span class="sxs-lookup"><span data-stu-id="cc69c-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="cc69c-131">Следующая таблица показывает языка поставщика констант, которые представляют идентификаторы GUID, обозначающие поставщиков языков программирования.</span><span class="sxs-lookup"><span data-stu-id="cc69c-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="cc69c-132">Символ</span><span class="sxs-lookup"><span data-stu-id="cc69c-132">Symbol</span></span>|<span data-ttu-id="cc69c-133">Описание</span><span class="sxs-lookup"><span data-stu-id="cc69c-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cc69c-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="cc69c-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="cc69c-135">Указывает корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc69c-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="cc69c-136">Константы типа документа</span><span class="sxs-lookup"><span data-stu-id="cc69c-136">Document Type Constants</span></span>  
 <span data-ttu-id="cc69c-137">Следующая таблица показывает документа тип константы, которые представляют идентификаторы GUID, которые идентифицируют типы документов.</span><span class="sxs-lookup"><span data-stu-id="cc69c-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="cc69c-138">Символ</span><span class="sxs-lookup"><span data-stu-id="cc69c-138">Symbol</span></span>|<span data-ttu-id="cc69c-139">Описание</span><span class="sxs-lookup"><span data-stu-id="cc69c-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cc69c-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="cc69c-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="cc69c-141">Указывает текстовый документ.</span><span class="sxs-lookup"><span data-stu-id="cc69c-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="cc69c-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="cc69c-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="cc69c-143">Указывает нетекстовый документ.</span><span class="sxs-lookup"><span data-stu-id="cc69c-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc69c-144">См. также</span><span class="sxs-lookup"><span data-stu-id="cc69c-144">See Also</span></span>  
 [<span data-ttu-id="cc69c-145">Справочник по неуправляемым API</span><span class="sxs-lookup"><span data-stu-id="cc69c-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
