---
title: Константы (справочные сведения о неуправляемых API)
ms.date: 03/30/2017
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
ms.openlocfilehash: 88dfdfcaee4a53e9b3c6e4b7e8187c8bfd5eaa13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099621"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="28efb-102">Константы (справочные сведения о неуправляемых API)</span><span class="sxs-lookup"><span data-stu-id="28efb-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="28efb-103">В этом разделе описывается тип языка, поставщик языка и константы типа документа, определенные в Корсим. idl.</span><span class="sxs-lookup"><span data-stu-id="28efb-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="28efb-104">Константы типа языка</span><span class="sxs-lookup"><span data-stu-id="28efb-104">Language Type Constants</span></span>  
 <span data-ttu-id="28efb-105">В следующей таблице показаны константы типа языка, представляющие идентификаторы GUID, которые определяют языки программирования.</span><span class="sxs-lookup"><span data-stu-id="28efb-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="28efb-106">Символ</span><span class="sxs-lookup"><span data-stu-id="28efb-106">Symbol</span></span>|<span data-ttu-id="28efb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="28efb-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="28efb-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="28efb-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="28efb-109">Указывает язык C.</span><span class="sxs-lookup"><span data-stu-id="28efb-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="28efb-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="28efb-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="28efb-111">Указывает C++ язык.</span><span class="sxs-lookup"><span data-stu-id="28efb-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="28efb-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="28efb-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="28efb-113">Указывает C# язык.</span><span class="sxs-lookup"><span data-stu-id="28efb-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="28efb-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="28efb-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="28efb-115">Указывает базовый язык.</span><span class="sxs-lookup"><span data-stu-id="28efb-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="28efb-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="28efb-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="28efb-117">Указывает язык Java.</span><span class="sxs-lookup"><span data-stu-id="28efb-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="28efb-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="28efb-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="28efb-119">Указывает язык COBOL.</span><span class="sxs-lookup"><span data-stu-id="28efb-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="28efb-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="28efb-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="28efb-121">Указывает на язык Pascal.</span><span class="sxs-lookup"><span data-stu-id="28efb-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="28efb-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="28efb-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="28efb-123">Указывает код сборки кода на языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="28efb-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="28efb-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="28efb-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="28efb-125">Указывает язык JScript.</span><span class="sxs-lookup"><span data-stu-id="28efb-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="28efb-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="28efb-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="28efb-127">Указывает на язык SMC.</span><span class="sxs-lookup"><span data-stu-id="28efb-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="28efb-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="28efb-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="28efb-129">Указывает C++ язык, включенный для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="28efb-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="28efb-130">Константы поставщика языка</span><span class="sxs-lookup"><span data-stu-id="28efb-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="28efb-131">В следующей таблице показаны константы поставщика языка, представляющие идентификаторы GUID, которые определяют поставщики языков программирования.</span><span class="sxs-lookup"><span data-stu-id="28efb-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="28efb-132">Символ</span><span class="sxs-lookup"><span data-stu-id="28efb-132">Symbol</span></span>|<span data-ttu-id="28efb-133">Описание</span><span class="sxs-lookup"><span data-stu-id="28efb-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="28efb-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="28efb-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="28efb-135">Указывает Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="28efb-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="28efb-136">Константы типов документов</span><span class="sxs-lookup"><span data-stu-id="28efb-136">Document Type Constants</span></span>  
 <span data-ttu-id="28efb-137">В следующей таблице показаны константы типа документа, представляющие идентификаторы GUID, которые определяют типы документов.</span><span class="sxs-lookup"><span data-stu-id="28efb-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="28efb-138">Символ</span><span class="sxs-lookup"><span data-stu-id="28efb-138">Symbol</span></span>|<span data-ttu-id="28efb-139">Описание</span><span class="sxs-lookup"><span data-stu-id="28efb-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="28efb-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="28efb-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="28efb-141">Указывает текстовый документ.</span><span class="sxs-lookup"><span data-stu-id="28efb-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="28efb-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="28efb-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="28efb-143">Указывает на нетекстовый документ.</span><span class="sxs-lookup"><span data-stu-id="28efb-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28efb-144">См. также</span><span class="sxs-lookup"><span data-stu-id="28efb-144">See also</span></span>

- [<span data-ttu-id="28efb-145">Справочник по неуправляемым API</span><span class="sxs-lookup"><span data-stu-id="28efb-145">Unmanaged API Reference</span></span>](index.md)
