---
title: "/ langversion (Visual Basic) | Документы Microsoft"
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
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: 8
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
ms.openlocfilehash: 56411df907bd5ff0416e6d0539cbe46df3b34947
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="langversion-visual-basic"></a><span data-ttu-id="7c6ff-102">/langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c6ff-102">/langversion (Visual Basic)</span></span>
<span data-ttu-id="7c6ff-103">Компилятор принимает только синтаксис, включенный в указанной версии языка Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7c6ff-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c6ff-104">Syntax</span></span>  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="7c6ff-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7c6ff-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="7c6ff-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7c6ff-106">Required.</span></span> <span data-ttu-id="7c6ff-107">Языковая версия для использования во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="7c6ff-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="7c6ff-108">Принимаются значения `9`, `9.0`, `10`, и `10.0`.</span><span class="sxs-lookup"><span data-stu-id="7c6ff-108">Accepted values are `9`, `9.0`, `10`, and `10.0`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c6ff-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c6ff-109">Remarks</span></span>  
 <span data-ttu-id="7c6ff-110">`/langversion` Указывает, какой синтаксис принимает компилятор.</span><span class="sxs-lookup"><span data-stu-id="7c6ff-110">The `/langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="7c6ff-111">Например если указать, что языковая версия является 9.0, компилятор создает ошибки для синтаксиса, применимого только в версии 10.0 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="7c6ff-111">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="7c6ff-112">Этот параметр можно использовать при разработке приложений, нацеленных на различные версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7c6ff-112">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="7c6ff-113">Например если вы используете .NET Framework 3.5, может использовать этот параметр, необходимо обеспечить использование синтаксиса языка версии 10.0.</span><span class="sxs-lookup"><span data-stu-id="7c6ff-113">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="7c6ff-114">Можно задать `/langversion` непосредственно только с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="7c6ff-114">You can set `/langversion` directly only by using the command line.</span></span> <span data-ttu-id="7c6ff-115">Дополнительные сведения см. в разделе [Указание конкретной версии или профиля .NET Framework](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="7c6ff-115">For more information, see [Targeting a Specific .NET Framework Version](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c6ff-116">Пример</span><span class="sxs-lookup"><span data-stu-id="7c6ff-116">Example</span></span>  
 <span data-ttu-id="7c6ff-117">Следующий код компилирует `sample.vb` для Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="7c6ff-117">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c6ff-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7c6ff-118">See Also</span></span>  
 <span data-ttu-id="7c6ff-119">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="7c6ff-119">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="7c6ff-120"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="7c6ff-120"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="7c6ff-121"> [Настройка конкретной версии платформы .NET Framework](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version)</span><span class="sxs-lookup"><span data-stu-id="7c6ff-121"> [Targeting a Specific .NET Framework Version](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version)</span></span>
