---
title: "Простые типы данных (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- elementary data types
- data types [Visual Basic], elementary
ms.assetid: dfad6fe9-2da6-49a4-b0b1-2d7ae0283de5
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6d363fdd7f7f2755aec34dfe82e38d83ba6e56af
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="elementary-data-types-visual-basic"></a><span data-ttu-id="781ae-102">Простые типы данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="781ae-102">Elementary Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="781ae-103">предоставляет набор стандартных типов данных, которые можно использовать для многих элементов программирования.</span><span class="sxs-lookup"><span data-stu-id="781ae-103"> supplies a set of predefined data types, which you can use for many of your programming elements.</span></span> <span data-ttu-id="781ae-104">В этом разделе описываются эти типы и способы их использования.</span><span class="sxs-lookup"><span data-stu-id="781ae-104">This section describes these types and how to use them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="781ae-105">Каждый простой тип данных в Visual Basic поддерживается структуры или класса, который находится в <xref:System>имен.</xref:System></span><span class="sxs-lookup"><span data-stu-id="781ae-105">Every elementary data type in Visual Basic is supported by a structure or a class that is in the <xref:System> namespace.</span></span> <span data-ttu-id="781ae-106">Компилятор использует каждое ключевое слово типа данных как псевдоним для базовой структуры или класса.</span><span class="sxs-lookup"><span data-stu-id="781ae-106">The compiler uses each data type keyword as an alias for the underlying structure or class.</span></span> <span data-ttu-id="781ae-107">Например, объявление переменной с помощью ключевого слова `Byte` является таким же, как его объявления с помощью полным именем структуры <xref:System.Byte?displayProperty=fullName>.</xref:System.Byte?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="781ae-107">For example, declaring a variable by using the reserved word `Byte` is the same as declaring it by using the fully qualified structure name <xref:System.Byte?displayProperty=fullName>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="781ae-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="781ae-108">In This Section</span></span>  
 [<span data-ttu-id="781ae-109">Числовые типы данных</span><span class="sxs-lookup"><span data-stu-id="781ae-109">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 <span data-ttu-id="781ae-110">Описание целых и не интегрированные числовых типов.</span><span class="sxs-lookup"><span data-stu-id="781ae-110">Describes the integral and non-integral numeric types.</span></span>  
  
 [<span data-ttu-id="781ae-111">Символьные типы данных</span><span class="sxs-lookup"><span data-stu-id="781ae-111">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 <span data-ttu-id="781ae-112">Описывает `Char` и `String` типов.</span><span class="sxs-lookup"><span data-stu-id="781ae-112">Describes the `Char` and `String` types.</span></span>  
  
 [<span data-ttu-id="781ae-113">Прочие типы данных</span><span class="sxs-lookup"><span data-stu-id="781ae-113">Miscellaneous Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)  
 <span data-ttu-id="781ae-114">Описывает `Boolean`, `Date`, и `Object` типы.</span><span class="sxs-lookup"><span data-stu-id="781ae-114">Describes the `Boolean`, `Date`, and `Object` types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="781ae-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="781ae-115">Related Sections</span></span>  
 [<span data-ttu-id="781ae-116">Типы данных</span><span class="sxs-lookup"><span data-stu-id="781ae-116">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="781ae-117">Представляет [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] типы данных и инструкции по их использованию.</span><span class="sxs-lookup"><span data-stu-id="781ae-117">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="781ae-118">Типы данных</span><span class="sxs-lookup"><span data-stu-id="781ae-118">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="781ae-119">Обзор простейших типов данных [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="781ae-119">Provides an overview of the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>
