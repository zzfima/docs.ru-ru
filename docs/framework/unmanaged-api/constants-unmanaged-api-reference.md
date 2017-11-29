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
ms.openlocfilehash: 45e4d41c16695010dc452d2f22850d43f885974a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="a24f7-102">Константы (справочные сведения о неуправляемых API)</span><span class="sxs-lookup"><span data-stu-id="a24f7-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="a24f7-103">В этом разделе описывается тип языка, поставщика языка и константы типа документа, которые определены в файле CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="a24f7-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="a24f7-104">Константы типа языка</span><span class="sxs-lookup"><span data-stu-id="a24f7-104">Language Type Constants</span></span>  
 <span data-ttu-id="a24f7-105">Следующая таблица показывает языка тип константы, которые представляют идентификаторы GUID, обозначающие языки программирования.</span><span class="sxs-lookup"><span data-stu-id="a24f7-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="a24f7-106">Символ</span><span class="sxs-lookup"><span data-stu-id="a24f7-106">Symbol</span></span>|<span data-ttu-id="a24f7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a24f7-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a24f7-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="a24f7-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="a24f7-109">Указывает язык C.</span><span class="sxs-lookup"><span data-stu-id="a24f7-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="a24f7-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="a24f7-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="a24f7-111">Указывает язык C++.</span><span class="sxs-lookup"><span data-stu-id="a24f7-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="a24f7-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="a24f7-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="a24f7-113">Указывает язык C#.</span><span class="sxs-lookup"><span data-stu-id="a24f7-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="a24f7-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="a24f7-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="a24f7-115">Указывает основной язык.</span><span class="sxs-lookup"><span data-stu-id="a24f7-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="a24f7-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="a24f7-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="a24f7-117">Указывает язык Java.</span><span class="sxs-lookup"><span data-stu-id="a24f7-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="a24f7-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="a24f7-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="a24f7-119">Указывает язык COBOL.</span><span class="sxs-lookup"><span data-stu-id="a24f7-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="a24f7-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="a24f7-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="a24f7-121">Указывает языка Pascal.</span><span class="sxs-lookup"><span data-stu-id="a24f7-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="a24f7-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="a24f7-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="a24f7-123">Указывает код сборки Microsoft промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="a24f7-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="a24f7-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="a24f7-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="a24f7-125">Указывает язык JScript.</span><span class="sxs-lookup"><span data-stu-id="a24f7-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="a24f7-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="a24f7-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="a24f7-127">Обозначает язык SMC.</span><span class="sxs-lookup"><span data-stu-id="a24f7-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="a24f7-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="a24f7-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="a24f7-129">Указывает язык C++ включена для платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a24f7-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="a24f7-130">Константы поставщиков языков</span><span class="sxs-lookup"><span data-stu-id="a24f7-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="a24f7-131">Следующая таблица показывает языка поставщика констант, которые представляют идентификаторы GUID, обозначающие поставщиков языков программирования.</span><span class="sxs-lookup"><span data-stu-id="a24f7-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="a24f7-132">Символ</span><span class="sxs-lookup"><span data-stu-id="a24f7-132">Symbol</span></span>|<span data-ttu-id="a24f7-133">Описание</span><span class="sxs-lookup"><span data-stu-id="a24f7-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a24f7-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="a24f7-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="a24f7-135">Указывает корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a24f7-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="a24f7-136">Константы типа документа</span><span class="sxs-lookup"><span data-stu-id="a24f7-136">Document Type Constants</span></span>  
 <span data-ttu-id="a24f7-137">Следующая таблица показывает документа тип константы, которые представляют идентификаторы GUID, которые идентифицируют типы документов.</span><span class="sxs-lookup"><span data-stu-id="a24f7-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="a24f7-138">Символ</span><span class="sxs-lookup"><span data-stu-id="a24f7-138">Symbol</span></span>|<span data-ttu-id="a24f7-139">Описание</span><span class="sxs-lookup"><span data-stu-id="a24f7-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a24f7-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="a24f7-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="a24f7-141">Указывает текстовый документ.</span><span class="sxs-lookup"><span data-stu-id="a24f7-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="a24f7-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="a24f7-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="a24f7-143">Указывает нетекстовый документ.</span><span class="sxs-lookup"><span data-stu-id="a24f7-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a24f7-144">См. также</span><span class="sxs-lookup"><span data-stu-id="a24f7-144">See Also</span></span>  
 [<span data-ttu-id="a24f7-145">Справочник по неуправляемым API</span><span class="sxs-lookup"><span data-stu-id="a24f7-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
