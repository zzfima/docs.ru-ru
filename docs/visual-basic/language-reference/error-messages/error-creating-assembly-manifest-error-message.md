---
title: "Ошибка при создании манифеста сборки: &lt;сообщение об ошибке&gt; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
dev_langs:
- VB
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
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
ms.openlocfilehash: 12e08feff09e901839c4e282d32a0a4e54e12576
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="7de48-102">Ошибка при создании манифеста сборки: &lt;сообщение об ошибке&gt;</span><span class="sxs-lookup"><span data-stu-id="7de48-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="7de48-103">Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] вызывает компоновщик сборок (Al.exe, который также называется Alink) для создания сборки с манифестом.</span><span class="sxs-lookup"><span data-stu-id="7de48-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="7de48-104">Компоновщик сообщил об ошибке на этапе предварительного выпуска процедуры создания сборки.</span><span class="sxs-lookup"><span data-stu-id="7de48-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="7de48-105">Такая ситуация может возникнуть при наличии проблем с указанным файлом ключа или контейнером ключей.</span><span class="sxs-lookup"><span data-stu-id="7de48-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="7de48-106">Чтобы использовать для сборки полную подпись, необходимо предоставить допустимый файл ключа с информацией об открытом и закрытом ключах.</span><span class="sxs-lookup"><span data-stu-id="7de48-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="7de48-107">Чтобы отложить подпись сборки, необходимо выбрать **отложенную подпись только** флажок и предоставить допустимый файл ключей, содержащий сведения об открытом ключе.</span><span class="sxs-lookup"><span data-stu-id="7de48-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="7de48-108">При использовании отложенной подписи для сборки наличие закрытого ключа не требуется.</span><span class="sxs-lookup"><span data-stu-id="7de48-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="7de48-109">Дополнительные сведения см. в разделе [как: подписать сборку (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span><span class="sxs-lookup"><span data-stu-id="7de48-109">For more information, see [How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span></span>  
  
 <span data-ttu-id="7de48-110">**Идентификатор ошибки:** BC30140</span><span class="sxs-lookup"><span data-stu-id="7de48-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7de48-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7de48-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="7de48-112">Просмотрите сообщение об ошибке и обратитесь к разделу [Al.exe ошибки и предупреждения средства](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) по ошибке AL1019 дополнительные пояснения и рекомендации</span><span class="sxs-lookup"><span data-stu-id="7de48-112">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="7de48-113">Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7de48-113">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de48-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7de48-114">See Also</span></span>  
 <span data-ttu-id="7de48-115">[Практическое руководство. Подписывание сборки (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564) </span><span class="sxs-lookup"><span data-stu-id="7de48-115">[How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564) </span></span>  
<span data-ttu-id="7de48-116"> [Страница "Подписывание" в конструкторе проектов](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer) </span><span class="sxs-lookup"><span data-stu-id="7de48-116"> [Signing Page, Project Designer](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer) </span></span>  
<span data-ttu-id="7de48-117"> [Al.exe (компоновщик сборок)](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="7de48-117"> [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="7de48-118"> [Ошибки и предупреждения программы Al.exe](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="7de48-118"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="7de48-119"> [Обращайтесь к нам](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="7de48-119"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
