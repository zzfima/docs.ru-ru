---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 82a7114027451d1342e6dc0846799933ce44d968
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="b3e27-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3e27-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="b3e27-103">Компилятор принимает только синтаксис, включенный в указанной версии языка Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b3e27-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3e27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3e27-104">Syntax</span></span>  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="b3e27-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b3e27-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="b3e27-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="b3e27-106">Required.</span></span> <span data-ttu-id="b3e27-107">Языковая версия для использования во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="b3e27-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="b3e27-108">Допустимые значения: `9`, `9.0`, `10`, и `10.0`.</span><span class="sxs-lookup"><span data-stu-id="b3e27-108">Accepted values are `9`, `9.0`, `10`, and `10.0`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3e27-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3e27-109">Remarks</span></span>  
 <span data-ttu-id="b3e27-110">`-langversion` Параметр указывает, какой синтаксис принимает компилятор.</span><span class="sxs-lookup"><span data-stu-id="b3e27-110">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="b3e27-111">Например если указать, что языковая версия является 9.0, компилятор создает ошибки синтаксиса, допустим только в версии 10.0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="b3e27-111">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="b3e27-112">Этот параметр можно использовать при разработке приложений, нацеленных на разные версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3e27-112">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="b3e27-113">Например если вы используете .NET Framework 3.5, можно позволяет этот параметр не следует использовать синтаксис из версии языка 10.0.</span><span class="sxs-lookup"><span data-stu-id="b3e27-113">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="b3e27-114">Можно задать `-langversion` непосредственно только с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="b3e27-114">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="b3e27-115">Дополнительные сведения см. в разделе [Указание конкретной версии или профиля .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="b3e27-115">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3e27-116">Пример</span><span class="sxs-lookup"><span data-stu-id="b3e27-116">Example</span></span>  
 <span data-ttu-id="b3e27-117">Следующий код компилирует `sample.vb` для Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="b3e27-117">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3e27-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b3e27-118">See Also</span></span>  
 [<span data-ttu-id="b3e27-119">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="b3e27-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b3e27-120">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="b3e27-120">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="b3e27-121">Настройка конкретной версии платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3e27-121">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
