---
title: '&lt;сообщение&gt; Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку &#39; &lt;assemblyname&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 498ca74497077e3268aa8cb25ce5121f3c9ea59d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588341"
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="7f619-102">&lt;сообщение&gt; Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку &#39; &lt;assemblyname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="7f619-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="7f619-103">\<сообщение > Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку "\<assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="7f619-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="7f619-104">В этом случае попробуйте заменить ссылку на файл "\<имя_файла_сборки >" в проекте "\<имя_проекта1 >" со ссылкой проекта "\<имя_проекта2 >".</span><span class="sxs-lookup"><span data-stu-id="7f619-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="7f619-105">Код в проекте обращается к члену другого проекта, но конфигурация решения не допускает компилятор Visual Basic разрешить ссылку.</span><span class="sxs-lookup"><span data-stu-id="7f619-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="7f619-106">Для доступа к типу, определенному в другой сборке, компилятор Visual Basic должен иметь ссылку на эту сборку.</span><span class="sxs-lookup"><span data-stu-id="7f619-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="7f619-107">Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.</span><span class="sxs-lookup"><span data-stu-id="7f619-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="7f619-108">**Идентификатор ошибки:** BC30971</span><span class="sxs-lookup"><span data-stu-id="7f619-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7f619-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7f619-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="7f619-110">Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="7f619-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="7f619-111">Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.</span><span class="sxs-lookup"><span data-stu-id="7f619-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="7f619-112">В свойствах проекта добавьте ссылку на проект, содержащий сборку, определяющую используемый тип.</span><span class="sxs-lookup"><span data-stu-id="7f619-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f619-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7f619-113">See Also</span></span>  
 [<span data-ttu-id="7f619-114">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="7f619-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="7f619-115">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="7f619-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [<span data-ttu-id="7f619-116">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="7f619-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="7f619-117">Диагностика неработающих ссылок</span><span class="sxs-lookup"><span data-stu-id="7f619-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
