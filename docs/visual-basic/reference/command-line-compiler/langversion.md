---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: db2cb1eb107973e9ce60ecb0d669c677d4fa2c51
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839729"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="d3006-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3006-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="d3006-103">Компилятор принимает только синтаксис, включенный в указанной версии языка Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d3006-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3006-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3006-104">Syntax</span></span>  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="d3006-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d3006-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="d3006-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d3006-106">Required.</span></span> <span data-ttu-id="d3006-107">Версия языка для использования во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="d3006-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="d3006-108">Принимаются значения `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` и `latest`.</span><span class="sxs-lookup"><span data-stu-id="d3006-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="d3006-109">Любой из целых чисел может также быть указан с помощью `.0` номер версии, например, `11.0`.</span><span class="sxs-lookup"><span data-stu-id="d3006-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="d3006-110">Можно просмотреть список всех возможных значений, указав `-langversion:?` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="d3006-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3006-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3006-111">Remarks</span></span>  
 <span data-ttu-id="d3006-112">`-langversion` Параметр указывает, какой синтаксис принимает компилятор.</span><span class="sxs-lookup"><span data-stu-id="d3006-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="d3006-113">Например если указать, что языковой версии является 9.0, компилятор выдает ошибки для синтаксис, который является допустимым только в версии 10.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="d3006-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="d3006-114">Этот параметр можно использовать при разработке приложения, ориентированные на разные версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3006-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="d3006-115">Например если вы ориентируетесь на .NET Framework 3.5, можно выполнить этот параметр, чтобы убедиться, что вы не используйте синтаксис с языковой версии 10.0.</span><span class="sxs-lookup"><span data-stu-id="d3006-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="d3006-116">Можно задать `-langversion` непосредственно только с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="d3006-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="d3006-117">Дополнительные сведения см. в разделе [Указание конкретной версии или профиля .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="d3006-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3006-118">Пример</span><span class="sxs-lookup"><span data-stu-id="d3006-118">Example</span></span>  
 <span data-ttu-id="d3006-119">Следующий код компилирует `sample.vb` для Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="d3006-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3006-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d3006-120">See also</span></span>

- [<span data-ttu-id="d3006-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d3006-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d3006-122">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d3006-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="d3006-123">Настройка конкретной версии платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d3006-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
