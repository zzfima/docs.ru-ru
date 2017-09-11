---
title: "/ delaysign | Документы Microsoft"
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
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: bcc819e08ca7731d91dc77dc831060bcf00a4425
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="delaysign"></a><span data-ttu-id="fe996-102">/delaysign</span><span class="sxs-lookup"><span data-stu-id="fe996-102">/delaysign</span></span>
<span data-ttu-id="fe996-103">Указывает, будет ли сборка полностью или частично подписана.</span><span class="sxs-lookup"><span data-stu-id="fe996-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe996-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe996-104">Syntax</span></span>  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fe996-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fe996-105">Arguments</span></span>  
 <span data-ttu-id="fe996-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="fe996-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="fe996-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="fe996-107">Optional.</span></span> <span data-ttu-id="fe996-108">Если требуется полностью подписанная сборка, используйте `/delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="fe996-108">Use `/delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="fe996-109">Используйте `/delaysign+` необходимо поместить открытый ключ в сборку и зарезервировать место для хэша подписи.</span><span class="sxs-lookup"><span data-stu-id="fe996-109">Use `/delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="fe996-110">Значение по умолчанию — `/delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="fe996-110">The default is `/delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe996-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fe996-111">Remarks</span></span>  
 <span data-ttu-id="fe996-112">`/delaysign` Не оказывает никакого влияния, если не используется с [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) или [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="fe996-112">The `/delaysign` option has no effect unless used with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="fe996-113">При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки) и подписывает хэш закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="fe996-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="fe996-114">Итоговая цифровая подпись хранится в файле, содержащем манифест.</span><span class="sxs-lookup"><span data-stu-id="fe996-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="fe996-115">Если применяется отложенная подпись сборки, компилятор вычислений и не сохраняет подпись, а резервирует место в файле для дальнейшего добавления подписи можно.</span><span class="sxs-lookup"><span data-stu-id="fe996-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="fe996-116">Например, с помощью `/delaysign+`, разработчик в организации может распространять неподписанные тестовые версии сборки, инженеры-испытатели могут зарегистрировать в глобальном кэше сборок и использовать.</span><span class="sxs-lookup"><span data-stu-id="fe996-116">For example, by using `/delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="fe996-117">После завершения работы по сборке лицо, ответственное за закрытый ключ организации можно полностью подписать сборку.</span><span class="sxs-lookup"><span data-stu-id="fe996-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="fe996-118">Это разделение ответственности защищает закрытый ключ организации от раскрытия, позволяя всем разработчикам работать со сборками.</span><span class="sxs-lookup"><span data-stu-id="fe996-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="fe996-119">В разделе [Создание и использование сборок](https://msdn.microsoft.com/library/xwb8f617) Дополнительные сведения о подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="fe996-119">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="fe996-120">Установка/delaysign в Visual Studio интегрированная среда разработки</span><span class="sxs-lookup"><span data-stu-id="fe996-120">To set /delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="fe996-121">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="fe996-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fe996-122">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="fe996-122">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="fe996-123">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="fe996-123">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="fe996-124">Щелкните **подписи** вкладки.</span><span class="sxs-lookup"><span data-stu-id="fe996-124">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="fe996-125">Задайте значение в **отложенную подпись только** поле.</span><span class="sxs-lookup"><span data-stu-id="fe996-125">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe996-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fe996-126">See Also</span></span>  
 <span data-ttu-id="fe996-127">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="fe996-127">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="fe996-128"> [/ keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="fe996-128"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="fe996-129"> [/ keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) </span><span class="sxs-lookup"><span data-stu-id="fe996-129"> [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) </span></span>  
<span data-ttu-id="fe996-130"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="fe996-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
