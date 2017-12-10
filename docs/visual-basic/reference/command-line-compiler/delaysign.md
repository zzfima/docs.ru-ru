---
title: /delaysign
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dc457a1a32048441f82976488158f223e7e3e087
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="delaysign"></a><span data-ttu-id="492dc-102">/delaysign</span><span class="sxs-lookup"><span data-stu-id="492dc-102">/delaysign</span></span>
<span data-ttu-id="492dc-103">Указывает, будет ли сборка полностью или частично подписана.</span><span class="sxs-lookup"><span data-stu-id="492dc-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="492dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="492dc-104">Syntax</span></span>  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="492dc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="492dc-105">Arguments</span></span>  
 <span data-ttu-id="492dc-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="492dc-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="492dc-107">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="492dc-107">Optional.</span></span> <span data-ttu-id="492dc-108">Если требуется полностью подписанная сборка, используйте `/delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="492dc-108">Use `/delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="492dc-109">Используйте `/delaysign+` требуется поместить открытый ключ в сборку и зарезервировать место для хэша подписи.</span><span class="sxs-lookup"><span data-stu-id="492dc-109">Use `/delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="492dc-110">Значение по умолчанию — `/delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="492dc-110">The default is `/delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="492dc-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="492dc-111">Remarks</span></span>  
 <span data-ttu-id="492dc-112">`/delaysign` Параметр действует только при использовании [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) или [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="492dc-112">The `/delaysign` option has no effect unless used with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="492dc-113">При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="492dc-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="492dc-114">Итоговая цифровая подпись хранится в файле, содержащем манифест.</span><span class="sxs-lookup"><span data-stu-id="492dc-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="492dc-115">При отложенной подписи сборки компилятор вычислений и не сохраняет подпись, а резервирует пространство в файле для последующего добавления подписи.</span><span class="sxs-lookup"><span data-stu-id="492dc-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="492dc-116">Например, с помощью `/delaysign+`, разработчик в организации может распространять неподписанные тестовые версии сборки, можно зарегистрировать в глобальном кэше сборок и использовать тест-инженеры.</span><span class="sxs-lookup"><span data-stu-id="492dc-116">For example, by using `/delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="492dc-117">После завершения работы по сборке лицо, ответственное за закрытый ключ организации можно полностью подписать сборку.</span><span class="sxs-lookup"><span data-stu-id="492dc-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="492dc-118">Это разделение ответственности защищает закрытый ключ организации от раскрытия, позволяя всем разработчикам работать со сборками.</span><span class="sxs-lookup"><span data-stu-id="492dc-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="492dc-119">В разделе [Создание и использование сборок](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) Дополнительные сведения о подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="492dc-119">See [Creating and Using Strong-Named Assemblies](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="492dc-120">Установка в Visual Studio/delaysign интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="492dc-120">To set /delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="492dc-121">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="492dc-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="492dc-122">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="492dc-122">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="492dc-123">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="492dc-123">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="492dc-124">Откройте вкладку **Подписывание**.</span><span class="sxs-lookup"><span data-stu-id="492dc-124">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="492dc-125">Задайте значение в **отложенную подпись только** поле.</span><span class="sxs-lookup"><span data-stu-id="492dc-125">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492dc-126">См. также</span><span class="sxs-lookup"><span data-stu-id="492dc-126">See Also</span></span>  
 [<span data-ttu-id="492dc-127">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="492dc-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="492dc-128">/keyfile</span><span class="sxs-lookup"><span data-stu-id="492dc-128">/keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="492dc-129">/keycontainer</span><span class="sxs-lookup"><span data-stu-id="492dc-129">/keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [<span data-ttu-id="492dc-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="492dc-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
