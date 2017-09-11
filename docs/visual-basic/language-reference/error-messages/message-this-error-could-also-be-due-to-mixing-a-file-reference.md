---
title: "&lt;сообщение&gt; Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку &quot;&lt;assemblyname&gt;&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
dev_langs:
- VB
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c0908b1a13b9b9c54fb533201404987e479c6138
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="f8569-102">&lt;сообщение&gt; Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку "&lt;assemblyname&gt;"</span><span class="sxs-lookup"><span data-stu-id="f8569-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="f8569-103">\<сообщение настроек Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку "\<assemblyname настроек.</span><span class="sxs-lookup"><span data-stu-id="f8569-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="f8569-104">В этом случае попробуйте заменить ссылку на файл "\<assemblyfilename настроек" в проекте "\<projectname1 настроек" со ссылкой на проект "\<projectname2 настроек".</span><span class="sxs-lookup"><span data-stu-id="f8569-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="f8569-105">Код в проекте обращается к члену другого проекта, но конфигурация решения не позволяет [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятора для разрешения ссылки.</span><span class="sxs-lookup"><span data-stu-id="f8569-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="f8569-106">Для доступа к типу, определенному в другой сборке, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор должен иметь ссылку на эту сборку.</span><span class="sxs-lookup"><span data-stu-id="f8569-106">To access a type defined in another assembly, the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="f8569-107">Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.</span><span class="sxs-lookup"><span data-stu-id="f8569-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="f8569-108">**Идентификатор ошибки:** BC30971</span><span class="sxs-lookup"><span data-stu-id="f8569-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f8569-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f8569-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="f8569-110">Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="f8569-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="f8569-111">Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.</span><span class="sxs-lookup"><span data-stu-id="f8569-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="f8569-112">В свойствах проекта добавьте ссылку на проект, содержащий сборку, определяющую используемый тип.</span><span class="sxs-lookup"><span data-stu-id="f8569-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8569-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f8569-113">See Also</span></span>  
 <span data-ttu-id="f8569-114">[Управление ссылками проекта](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="f8569-114">[Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="f8569-115"> [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="f8569-115"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="f8569-116"> [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылки"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="f8569-116"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="f8569-117"> [NIB Практическое руководство: изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="f8569-117"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="f8569-118"> [Диагностика неработающих ссылок](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span><span class="sxs-lookup"><span data-stu-id="f8569-118"> [Troubleshooting Broken References](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span></span>
