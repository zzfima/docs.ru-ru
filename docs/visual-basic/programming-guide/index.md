---
title: "Руководство по программированию на Visual Basic"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, language guide
- Visual Basic, programming in
- Visual Basic, language reference
ms.assetid: 640e5796-2796-433c-af37-4d2a2334895b
caps.latest.revision: 19
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 01d6a1fc688f2cdf55ab4be5c6d0a8daccda2031
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="visual-basic-programming-guide"></a><span data-ttu-id="9ec9d-102">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ec9d-102">Visual Basic Programming Guide</span></span>
<span data-ttu-id="9ec9d-103">Как и любой современный язык программирования, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] поддерживает множество общих программных конструкций и элементов языка.</span><span class="sxs-lookup"><span data-stu-id="9ec9d-103">As with any modern programming language, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supports many common programming constructs and language elements.</span></span> <span data-ttu-id="9ec9d-104">Это руководство описывает все основные элементы программирования на [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ec9d-104">This guide describes all the major elements of programming with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ec9d-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="9ec9d-105">In This Section</span></span>  
 [<span data-ttu-id="9ec9d-106">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="9ec9d-106">Program Structure and Code Conventions</span></span>](../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 <span data-ttu-id="9ec9d-107">Содержит документацию по базовой структуре и соглашениям кода [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], таким как соглашения об именовании, комментарии в коде и действующие в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ограничения.</span><span class="sxs-lookup"><span data-stu-id="9ec9d-107">Contains documentation on the basic structure and code conventions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], such as naming conventions, comments in code, and limitations within [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 [<span data-ttu-id="9ec9d-108">Возможности и элементы языка Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ec9d-108">Visual Basic Language Features</span></span>](../../visual-basic/programming-guide/language-features/index.md)  
 <span data-ttu-id="9ec9d-109">Содержит ссылки на разделы с описанием важных компонентов [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], включая LINQ и XML-литералы.</span><span class="sxs-lookup"><span data-stu-id="9ec9d-109">Provides links to topics that introduce and discuss important features of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], including LINQ and XML literals.</span></span>  
  
 [<span data-ttu-id="9ec9d-110">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="9ec9d-110">COM Interop</span></span>](../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="9ec9d-111">Поясняет проблемы взаимодействия, связанные с созданием и использованием объектов модели COM в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ec9d-111">Explains the interoperability issues associated with creating and using component object model (COM) objects with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9ec9d-112">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9ec9d-112">Related Sections</span></span>  
 [<span data-ttu-id="9ec9d-113">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ec9d-113">Visual Basic Language Reference</span></span>](../../visual-basic/language-reference/index.md)  
 <span data-ttu-id="9ec9d-114">Содержит справочные сведения о различных аспектах программирования на [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ec9d-114">Provides reference information about various aspects of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programming.</span></span>  
  
 [<span data-ttu-id="9ec9d-115">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="9ec9d-115">Visual Basic Command-Line Compiler</span></span>](../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="9ec9d-116">Содержит информацию об использовании компилятора командной строки [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], его параметров и инструмента обновления ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="9ec9d-116">Offers information on using the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] command-line compiler, the compiler options, and the Keyword Upgrade tool.</span></span>

