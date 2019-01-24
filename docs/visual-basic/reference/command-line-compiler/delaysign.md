---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 1a784dc57331ed4cbaeb8524dbb3b6ea9a06eca1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605595"
---
# <a name="-delaysign"></a><span data-ttu-id="a202a-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="a202a-102">-delaysign</span></span>
<span data-ttu-id="a202a-103">Указывает, будет ли сборка полностью или частично подписана.</span><span class="sxs-lookup"><span data-stu-id="a202a-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a202a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a202a-104">Syntax</span></span>  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a202a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a202a-105">Arguments</span></span>  
 <span data-ttu-id="a202a-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a202a-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="a202a-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="a202a-107">Optional.</span></span> <span data-ttu-id="a202a-108">Если требуется полностью подписанная сборка, используйте `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="a202a-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="a202a-109">Используйте `-delaysign+` Если вы хотите поместить открытый ключ в сборку и зарезервировать место для хэша подписи.</span><span class="sxs-lookup"><span data-stu-id="a202a-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="a202a-110">Значение по умолчанию — `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="a202a-110">The default is `-delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a202a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="a202a-111">Remarks</span></span>  
 <span data-ttu-id="a202a-112">`-delaysign` Никак не действует, за исключением применения с [- keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) или [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="a202a-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="a202a-113">При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="a202a-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="a202a-114">Итоговая цифровая подпись хранится в файле, содержащем манифест.</span><span class="sxs-lookup"><span data-stu-id="a202a-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="a202a-115">При отложенной подписи сборки компилятор вычисляет и не сохраняет подпись, но резервирует пространство в файле, чтобы подпись можно добавить позже.</span><span class="sxs-lookup"><span data-stu-id="a202a-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="a202a-116">Например, с помощью `-delaysign+`, разработчик в организации можно распространять без знака тестовых версий сборки, можно зарегистрировать в глобальном кэше сборок и использовать тест-инженеров.</span><span class="sxs-lookup"><span data-stu-id="a202a-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="a202a-117">После завершения работы по сборке лицо, ответственное за закрытый ключ организации можно полностью подписать сборку.</span><span class="sxs-lookup"><span data-stu-id="a202a-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="a202a-118">Это разделение ответственности защищает закрытый ключ организации от раскрытия, позволяя всем разработчикам возможность работать со сборками.</span><span class="sxs-lookup"><span data-stu-id="a202a-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="a202a-119">См. в разделе [Создание и использование сборок со строгими именами](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) Дополнительные сведения о подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="a202a-119">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="a202a-120">Чтобы задать - delaysign в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a202a-120">To set -delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="a202a-121">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="a202a-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a202a-122">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a202a-122">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="a202a-123">Откройте вкладку **Подписывание**.</span><span class="sxs-lookup"><span data-stu-id="a202a-123">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="a202a-124">Задайте значение в **только отложенная подпись** поле.</span><span class="sxs-lookup"><span data-stu-id="a202a-124">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a202a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a202a-125">See also</span></span>
- [<span data-ttu-id="a202a-126">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="a202a-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a202a-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="a202a-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="a202a-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="a202a-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [<span data-ttu-id="a202a-129">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="a202a-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
