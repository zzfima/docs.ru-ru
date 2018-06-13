---
title: Требуется ссылка на сборку &#39; &lt;assemblyidentity&gt; &#39; содержащий тип &#39; &lt;typename&gt;&#39;, но подходящая ссылка не удалось найти из-за неоднозначности между проекты &#39; &lt;имя_проекта1&gt; &#39; и &#39; &lt;имя_проекта2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 670ac3ceb6a703a11b8f00a341dbcf868d4ceb7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597449"
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a><span data-ttu-id="fe4fa-102">Требуется ссылка на сборку &#39; &lt;assemblyidentity&gt; &#39; содержащий тип &#39; &lt;typename&gt;&#39;, но подходящая ссылка не удалось найти из-за неоднозначности между проекты &#39; &lt;имя_проекта1&gt; &#39; и &#39; &lt;имя_проекта2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="fe4fa-102">Reference required to assembly &#39;&lt;assemblyidentity&gt;&#39; containing type &#39;&lt;typename&gt;&#39;, but a suitable reference could not be found due to ambiguity between projects &#39;&lt;projectname1&gt;&#39; and &#39;&lt;projectname2&gt;&#39;</span></span>
<span data-ttu-id="fe4fa-103">Выражение использует тип, например класс, структуру, интерфейс, перечисление или делегат, который определен за пределами проекта.</span><span class="sxs-lookup"><span data-stu-id="fe4fa-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="fe4fa-104">Однако имеются ссылки проекта на несколько сборок, определяющих этот тип.</span><span class="sxs-lookup"><span data-stu-id="fe4fa-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="fe4fa-105">Названные проекты создают сборки с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="fe4fa-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="fe4fa-106">Поэтому компилятор не может определить, какую сборку следует использовать для типа, к которому осуществляется доступ.</span><span class="sxs-lookup"><span data-stu-id="fe4fa-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="fe4fa-107">Для доступа к типу, определенному в другой сборке, компилятор Visual Basic должен иметь ссылку на эту сборку.</span><span class="sxs-lookup"><span data-stu-id="fe4fa-107">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="fe4fa-108">Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.</span><span class="sxs-lookup"><span data-stu-id="fe4fa-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="fe4fa-109">**Идентификатор ошибки:** BC30969</span><span class="sxs-lookup"><span data-stu-id="fe4fa-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fe4fa-110">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="fe4fa-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="fe4fa-111">Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="fe4fa-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="fe4fa-112">Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.</span><span class="sxs-lookup"><span data-stu-id="fe4fa-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="fe4fa-113">В свойствах проекта добавьте ссылку на файл, содержащий сборку, определяющую используемый тип.</span><span class="sxs-lookup"><span data-stu-id="fe4fa-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4fa-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fe4fa-114">See Also</span></span>  
 [<span data-ttu-id="fe4fa-115">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="fe4fa-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="fe4fa-116">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="fe4fa-116">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [<span data-ttu-id="fe4fa-117">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="fe4fa-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="fe4fa-118">Диагностика неработающих ссылок</span><span class="sxs-lookup"><span data-stu-id="fe4fa-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
