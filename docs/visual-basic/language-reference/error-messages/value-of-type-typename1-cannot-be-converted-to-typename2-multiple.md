---
title: Значение типа &#39; &lt;Имя_типа1&gt; &#39; невозможно преобразовать в &#39; &lt;имя_типа2&gt; &#39; (множественные ссылки на файл)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 943b9612a9217b90c19f34285e812c4e1cccf81a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691379"
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="6658b-102">Значение типа &#39; &lt;Имя_типа1&gt; &#39; невозможно преобразовать в &#39; &lt;имя_типа2&gt; &#39; (множественные ссылки на файл)</span><span class="sxs-lookup"><span data-stu-id="6658b-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="6658b-103">Значение типа "\<Имя_типа1 >" нельзя преобразовать в "\<имя_типа2 >".</span><span class="sxs-lookup"><span data-stu-id="6658b-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="6658b-104">Несоответствие типов может быть вызвана смешением ссылки на файл "\<путь_к_файлу1 >" в проекте "\<имя_проекта1 >" с помощью ссылки на файл "\<путь_к_файлу2 >" в проекте "\<имя_проекта2 >".</span><span class="sxs-lookup"><span data-stu-id="6658b-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="6658b-105">Если обе сборки идентичны, попробуйте заменить эти ссылки так, чтобы они ссылались из одного места.</span><span class="sxs-lookup"><span data-stu-id="6658b-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="6658b-106">В ситуации, когда проект делает более одной ссылки на сборку компилятор не может гарантировать, что один тип может быть преобразован в другой.</span><span class="sxs-lookup"><span data-stu-id="6658b-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="6658b-107">Каждая ссылка на файл указывает путь к файлу и имя для выходного файла проекта (как правило, файл DLL).</span><span class="sxs-lookup"><span data-stu-id="6658b-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="6658b-108">Компилятор не может гарантировать, что выходные файлы входят из одного источника, и что они представляют одну и ту же версию той же сборки.</span><span class="sxs-lookup"><span data-stu-id="6658b-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="6658b-109">Таким образом он не может гарантировать, что типы в различные ссылки относятся к одному типу, или даже в том, что один могут быть преобразованы в другой.</span><span class="sxs-lookup"><span data-stu-id="6658b-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="6658b-110">Если вы знаете, что указанные сборки имеют тот же идентификатор сборки, можно использовать ссылку на один файл.</span><span class="sxs-lookup"><span data-stu-id="6658b-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="6658b-111">*Удостоверение сборки* включает имя сборки, версию, открытый ключ (при его наличии), язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="6658b-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="6658b-112">Эти сведения уникально идентифицируют сборку.</span><span class="sxs-lookup"><span data-stu-id="6658b-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="6658b-113">**Идентификатор ошибки:** BC30961</span><span class="sxs-lookup"><span data-stu-id="6658b-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6658b-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6658b-114">To correct this error</span></span>  
  
-   <span data-ttu-id="6658b-115">Если указанные сборки имеют тот же идентификатор сборки, удалите или замените один из ссылки на файлы, таким образом, что только одна ссылка на файл.</span><span class="sxs-lookup"><span data-stu-id="6658b-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="6658b-116">Если эти сборки не имеют тот же идентификатор сборки, а затем изменить код таким образом, чтобы он не пытается преобразовать тип в одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="6658b-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6658b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6658b-117">See also</span></span>
- [<span data-ttu-id="6658b-118">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6658b-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="6658b-119">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="6658b-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)

