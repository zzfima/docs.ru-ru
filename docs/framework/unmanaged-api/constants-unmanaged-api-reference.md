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
ms.openlocfilehash: 8c76db644ffee478003d834460c155c4ec6d0070
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944616"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="75ef8-102">Константы (справочные сведения о неуправляемых API)</span><span class="sxs-lookup"><span data-stu-id="75ef8-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="75ef8-103">В этом разделе описывается тип языка, поставщика языка и константы типа документа, определяемые в CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="75ef8-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="75ef8-104">Константы типа языка</span><span class="sxs-lookup"><span data-stu-id="75ef8-104">Language Type Constants</span></span>  
 <span data-ttu-id="75ef8-105">Следующая таблица показывает языка константы типа, которые представляют идентификаторы GUID, которые идентифицируют языков программирования.</span><span class="sxs-lookup"><span data-stu-id="75ef8-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="75ef8-106">Символ</span><span class="sxs-lookup"><span data-stu-id="75ef8-106">Symbol</span></span>|<span data-ttu-id="75ef8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="75ef8-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="75ef8-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="75ef8-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="75ef8-109">Указывает язык C.</span><span class="sxs-lookup"><span data-stu-id="75ef8-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="75ef8-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="75ef8-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="75ef8-111">Указывает язык C++.</span><span class="sxs-lookup"><span data-stu-id="75ef8-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="75ef8-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="75ef8-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="75ef8-113">Указывает C# языка.</span><span class="sxs-lookup"><span data-stu-id="75ef8-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="75ef8-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="75ef8-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="75ef8-115">Указывает базовый язык.</span><span class="sxs-lookup"><span data-stu-id="75ef8-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="75ef8-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="75ef8-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="75ef8-117">Указывает на языке Java.</span><span class="sxs-lookup"><span data-stu-id="75ef8-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="75ef8-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="75ef8-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="75ef8-119">Указывает язык COBOL.</span><span class="sxs-lookup"><span data-stu-id="75ef8-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="75ef8-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="75ef8-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="75ef8-121">Указывает язык, Pascal.</span><span class="sxs-lookup"><span data-stu-id="75ef8-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="75ef8-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="75ef8-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="75ef8-123">Указывает код сборки Microsoft промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="75ef8-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="75ef8-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="75ef8-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="75ef8-125">Указывает язык JScript.</span><span class="sxs-lookup"><span data-stu-id="75ef8-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="75ef8-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="75ef8-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="75ef8-127">Указывает язык SMC.</span><span class="sxs-lookup"><span data-stu-id="75ef8-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="75ef8-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="75ef8-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="75ef8-129">Указывает язык C++ для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75ef8-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="75ef8-130">Константы поставщиков языков</span><span class="sxs-lookup"><span data-stu-id="75ef8-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="75ef8-131">Следующая таблица показывает языка константы поставщиков, которые представляют идентификаторы GUID, которые идентифицируют поставщиков языков программирования.</span><span class="sxs-lookup"><span data-stu-id="75ef8-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="75ef8-132">Символ</span><span class="sxs-lookup"><span data-stu-id="75ef8-132">Symbol</span></span>|<span data-ttu-id="75ef8-133">Описание</span><span class="sxs-lookup"><span data-stu-id="75ef8-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="75ef8-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="75ef8-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="75ef8-135">Указывает Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75ef8-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="75ef8-136">Константы типа документа</span><span class="sxs-lookup"><span data-stu-id="75ef8-136">Document Type Constants</span></span>  
 <span data-ttu-id="75ef8-137">Следующая таблица показывает документа константы типа, которые представляют идентификаторы GUID, которые идентифицируют типы документов.</span><span class="sxs-lookup"><span data-stu-id="75ef8-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="75ef8-138">Символ</span><span class="sxs-lookup"><span data-stu-id="75ef8-138">Symbol</span></span>|<span data-ttu-id="75ef8-139">Описание</span><span class="sxs-lookup"><span data-stu-id="75ef8-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="75ef8-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="75ef8-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="75ef8-141">Указывает текстовый документ.</span><span class="sxs-lookup"><span data-stu-id="75ef8-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="75ef8-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="75ef8-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="75ef8-143">Указывает не текстовый документ.</span><span class="sxs-lookup"><span data-stu-id="75ef8-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75ef8-144">См. также</span><span class="sxs-lookup"><span data-stu-id="75ef8-144">See also</span></span>

- [<span data-ttu-id="75ef8-145">Справочник по неуправляемым API</span><span class="sxs-lookup"><span data-stu-id="75ef8-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
