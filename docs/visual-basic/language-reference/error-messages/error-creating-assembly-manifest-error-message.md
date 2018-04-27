---
title: 'Ошибка при создании манифеста сборки: &lt;сообщение об ошибке&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4032bbcbf9924eb5aad4e2cb1a6e74df9a472eca
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="c47a8-102">Ошибка при создании манифеста сборки: &lt;сообщение об ошибке&gt;</span><span class="sxs-lookup"><span data-stu-id="c47a8-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="c47a8-103">Компилятор Visual Basic вызывает компоновщик сборок (Al.exe, который также называется Alink) для создания сборки с манифестом.</span><span class="sxs-lookup"><span data-stu-id="c47a8-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="c47a8-104">Компоновщик сообщил об ошибке на этапе предварительного выпуска процедуры создания сборки.</span><span class="sxs-lookup"><span data-stu-id="c47a8-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="c47a8-105">Такая ситуация может возникнуть при наличии проблем с указанным файлом ключа или контейнером ключей.</span><span class="sxs-lookup"><span data-stu-id="c47a8-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="c47a8-106">Чтобы использовать для сборки полную подпись, необходимо предоставить допустимый файл ключа с информацией об открытом и закрытом ключах.</span><span class="sxs-lookup"><span data-stu-id="c47a8-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="c47a8-107">Чтобы использовать для сборки отложенную подпись, необходимо установить флажок **Только отложенная подпись** и предоставить допустимый файл ключа с информацией о ключах.</span><span class="sxs-lookup"><span data-stu-id="c47a8-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="c47a8-108">При использовании отложенной подписи для сборки наличие закрытого ключа не требуется.</span><span class="sxs-lookup"><span data-stu-id="c47a8-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="c47a8-109">Дополнительные сведения см. в разделе [Практическое руководство. Подписание сборки строгим именем](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="c47a8-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
 <span data-ttu-id="c47a8-110">**Идентификатор ошибки:** BC30140</span><span class="sxs-lookup"><span data-stu-id="c47a8-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c47a8-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c47a8-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="c47a8-112">Просмотрите сообщение об ошибке и обратитесь к разделу [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="c47a8-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="c47a8-113">Ошибка AL1019 дополнительные пояснения и рекомендации</span><span class="sxs-lookup"><span data-stu-id="c47a8-113">for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="c47a8-114">Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c47a8-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c47a8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c47a8-115">See Also</span></span>  
 [<span data-ttu-id="c47a8-116">Практическое руководство. Подписание сборки строгим именем</span><span class="sxs-lookup"><span data-stu-id="c47a8-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="c47a8-117">Страница "Подписывание" в конструкторе проектов</span><span class="sxs-lookup"><span data-stu-id="c47a8-117">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 <span data-ttu-id="c47a8-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="c47a8-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 [<span data-ttu-id="c47a8-119">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="c47a8-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
