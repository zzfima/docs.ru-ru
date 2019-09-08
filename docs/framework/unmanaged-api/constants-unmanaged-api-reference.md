---
title: Константы (справочные сведения о неуправляемых API)
ms.date: 03/30/2017
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b91f2a749557f94a68f1929d649824719160d9ee
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786957"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="fbec2-102">Константы (справочные сведения о неуправляемых API)</span><span class="sxs-lookup"><span data-stu-id="fbec2-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="fbec2-103">В этом разделе описывается тип языка, поставщик языка и константы типа документа, определенные в Корсим. idl.</span><span class="sxs-lookup"><span data-stu-id="fbec2-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="fbec2-104">Константы типа языка</span><span class="sxs-lookup"><span data-stu-id="fbec2-104">Language Type Constants</span></span>  
 <span data-ttu-id="fbec2-105">В следующей таблице показаны константы типа языка, представляющие идентификаторы GUID, которые определяют языки программирования.</span><span class="sxs-lookup"><span data-stu-id="fbec2-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="fbec2-106">Символ</span><span class="sxs-lookup"><span data-stu-id="fbec2-106">Symbol</span></span>|<span data-ttu-id="fbec2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fbec2-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fbec2-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="fbec2-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="fbec2-109">Указывает язык C.</span><span class="sxs-lookup"><span data-stu-id="fbec2-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="fbec2-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="fbec2-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="fbec2-111">Указывает C++ язык.</span><span class="sxs-lookup"><span data-stu-id="fbec2-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="fbec2-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="fbec2-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="fbec2-113">Указывает C# язык.</span><span class="sxs-lookup"><span data-stu-id="fbec2-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="fbec2-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="fbec2-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="fbec2-115">Указывает базовый язык.</span><span class="sxs-lookup"><span data-stu-id="fbec2-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="fbec2-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="fbec2-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="fbec2-117">Указывает язык Java.</span><span class="sxs-lookup"><span data-stu-id="fbec2-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="fbec2-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="fbec2-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="fbec2-119">Указывает язык COBOL.</span><span class="sxs-lookup"><span data-stu-id="fbec2-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="fbec2-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="fbec2-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="fbec2-121">Указывает на язык Pascal.</span><span class="sxs-lookup"><span data-stu-id="fbec2-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="fbec2-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="fbec2-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="fbec2-123">Указывает код сборки кода на языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="fbec2-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="fbec2-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="fbec2-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="fbec2-125">Указывает язык JScript.</span><span class="sxs-lookup"><span data-stu-id="fbec2-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="fbec2-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="fbec2-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="fbec2-127">Указывает на язык SMC.</span><span class="sxs-lookup"><span data-stu-id="fbec2-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="fbec2-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="fbec2-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="fbec2-129">Указывает C++ язык, включенный для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fbec2-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="fbec2-130">Константы поставщика языка</span><span class="sxs-lookup"><span data-stu-id="fbec2-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="fbec2-131">В следующей таблице показаны константы поставщика языка, представляющие идентификаторы GUID, которые определяют поставщики языков программирования.</span><span class="sxs-lookup"><span data-stu-id="fbec2-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="fbec2-132">Символ</span><span class="sxs-lookup"><span data-stu-id="fbec2-132">Symbol</span></span>|<span data-ttu-id="fbec2-133">Описание</span><span class="sxs-lookup"><span data-stu-id="fbec2-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fbec2-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="fbec2-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="fbec2-135">Указывает Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fbec2-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="fbec2-136">Константы типов документов</span><span class="sxs-lookup"><span data-stu-id="fbec2-136">Document Type Constants</span></span>  
 <span data-ttu-id="fbec2-137">В следующей таблице показаны константы типа документа, представляющие идентификаторы GUID, которые определяют типы документов.</span><span class="sxs-lookup"><span data-stu-id="fbec2-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="fbec2-138">Символ</span><span class="sxs-lookup"><span data-stu-id="fbec2-138">Symbol</span></span>|<span data-ttu-id="fbec2-139">Описание</span><span class="sxs-lookup"><span data-stu-id="fbec2-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fbec2-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="fbec2-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="fbec2-141">Указывает текстовый документ.</span><span class="sxs-lookup"><span data-stu-id="fbec2-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="fbec2-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="fbec2-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="fbec2-143">Указывает на нетекстовый документ.</span><span class="sxs-lookup"><span data-stu-id="fbec2-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fbec2-144">См. также</span><span class="sxs-lookup"><span data-stu-id="fbec2-144">See also</span></span>

- [<span data-ttu-id="fbec2-145">Справочник по неуправляемым API</span><span class="sxs-lookup"><span data-stu-id="fbec2-145">Unmanaged API Reference</span></span>](index.md)
