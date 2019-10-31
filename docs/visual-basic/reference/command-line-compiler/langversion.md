---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 5f59f1c4c269a52131a324bbd2bfbe817ab794a4
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197086"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="8af9a-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8af9a-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="8af9a-103">Приводит к тому, что компилятор принимает только синтаксис, включенный в указанную языковую версию Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8af9a-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8af9a-104">Syntax</span></span>  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="8af9a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8af9a-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="8af9a-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8af9a-106">Required.</span></span> <span data-ttu-id="8af9a-107">Языковая версия, используемая во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="8af9a-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="8af9a-108">Допустимые значения: `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` и `latest`.</span><span class="sxs-lookup"><span data-stu-id="8af9a-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="8af9a-109">Любое из целых чисел можно также указать с помощью `.0` в качестве дополнительной версии, например `11.0`.</span><span class="sxs-lookup"><span data-stu-id="8af9a-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="8af9a-110">Чтобы просмотреть список всех возможных значений, укажите `-langversion:?` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="8af9a-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8af9a-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="8af9a-111">Remarks</span></span>  
 <span data-ttu-id="8af9a-112">Параметр `-langversion` указывает синтаксис, принимаемый компилятором.</span><span class="sxs-lookup"><span data-stu-id="8af9a-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="8af9a-113">Например, если указать, что языковая версия — 9,0, компилятор выдает ошибки для синтаксиса, который допустим только в версии 10,0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="8af9a-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="8af9a-114">Этот параметр можно использовать при разработке приложений, предназначенных для разных версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8af9a-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="8af9a-115">Например, если вы нацелены на .NET Framework 3,5, можно использовать этот параметр, чтобы не использовать синтаксис из языковой версии 10,0.</span><span class="sxs-lookup"><span data-stu-id="8af9a-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="8af9a-116">Вы можете задать `-langversion` напрямую только с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="8af9a-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="8af9a-117">Дополнительные сведения см. в разделе [Указание конкретной версии или профиля .NET Framework](/visualstudio/ide/visual-studio-multi-targeting-overview).</span><span class="sxs-lookup"><span data-stu-id="8af9a-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/visual-studio-multi-targeting-overview).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8af9a-118">Пример</span><span class="sxs-lookup"><span data-stu-id="8af9a-118">Example</span></span>  
 <span data-ttu-id="8af9a-119">Следующий код компилирует `sample.vb` для Visual Basic 9,0.</span><span class="sxs-lookup"><span data-stu-id="8af9a-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8af9a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8af9a-120">See also</span></span>

- [<span data-ttu-id="8af9a-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="8af9a-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8af9a-122">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="8af9a-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="8af9a-123">Настройка конкретной версии платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8af9a-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/visual-studio-multi-targeting-overview)
