---
title: "Ошибка при создании манифеста сборки: &lt;сообщение об ошибке&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords: BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d846ef88f0c36b49e79b9d11252fcef419dfa0ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="95057-102">Ошибка при создании манифеста сборки: &lt;сообщение об ошибке&gt;</span><span class="sxs-lookup"><span data-stu-id="95057-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="95057-103">Компилятор [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] вызывает компоновщик сборок (Al.exe, который также называется Alink) для создания сборки с манифестом.</span><span class="sxs-lookup"><span data-stu-id="95057-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="95057-104">Компоновщик сообщил об ошибке на этапе предварительного выпуска процедуры создания сборки.</span><span class="sxs-lookup"><span data-stu-id="95057-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="95057-105">Такая ситуация может возникнуть при наличии проблем с указанным файлом ключа или контейнером ключей.</span><span class="sxs-lookup"><span data-stu-id="95057-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="95057-106">Чтобы использовать для сборки полную подпись, необходимо предоставить допустимый файл ключа с информацией об открытом и закрытом ключах.</span><span class="sxs-lookup"><span data-stu-id="95057-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="95057-107">Чтобы использовать для сборки отложенную подпись, необходимо установить флажок **Только отложенная подпись** и предоставить допустимый файл ключа с информацией о ключах.</span><span class="sxs-lookup"><span data-stu-id="95057-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="95057-108">При использовании отложенной подписи для сборки наличие закрытого ключа не требуется.</span><span class="sxs-lookup"><span data-stu-id="95057-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="95057-109">Дополнительные сведения см. в разделе [как: подписать сборку (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span><span class="sxs-lookup"><span data-stu-id="95057-109">For more information, see [How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span></span>  
  
 <span data-ttu-id="95057-110">**Идентификатор ошибки:** BC30140</span><span class="sxs-lookup"><span data-stu-id="95057-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="95057-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="95057-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="95057-112">Просмотрите сообщение об ошибке и обратитесь к разделу [Al.exe ошибки и предупреждения средства](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) ошибка AL1019 дополнительные пояснения и рекомендации</span><span class="sxs-lookup"><span data-stu-id="95057-112">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="95057-113">Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="95057-113">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95057-114">См. также</span><span class="sxs-lookup"><span data-stu-id="95057-114">See Also</span></span>  
 [<span data-ttu-id="95057-115">Практическое руководство. Подписывание сборки (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="95057-115">How to: Sign an Assembly (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)  
 [<span data-ttu-id="95057-116">Страница "Подписывание" в конструкторе проектов</span><span class="sxs-lookup"><span data-stu-id="95057-116">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 [<span data-ttu-id="95057-117">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="95057-117">Al.exe (Assembly Linker)</span></span>](https://msdn.microsoft.com/library/c405shex)  
 [<span data-ttu-id="95057-118">Ошибки и предупреждения программы Al.exe</span><span class="sxs-lookup"><span data-stu-id="95057-118">Al.exe Tool Errors and Warnings</span></span>](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [<span data-ttu-id="95057-119">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="95057-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
