---
title: Значение типа &#39; &lt;Имя_типа1&gt; &#39; не может быть преобразован &#39; &lt;имя_типа2&gt; &#39; (несколько ссылок на файлы)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 41c18160be9b546f8b525376fa06bc0eca6c117a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603695"
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="f0167-102">Значение типа &#39; &lt;Имя_типа1&gt; &#39; не может быть преобразован &#39; &lt;имя_типа2&gt; &#39; (несколько ссылок на файлы)</span><span class="sxs-lookup"><span data-stu-id="f0167-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="f0167-103">Значение типа "\<Имя_типа1 >" нельзя преобразовать в "\<имя_типа2 >".</span><span class="sxs-lookup"><span data-stu-id="f0167-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="f0167-104">Несоответствие типов может быть вызвана смешением ссылки на файл "\<путь_к_файлу1 >" в проекте "\<имя_проекта1 >" со ссылкой на файл "\<путь_к_файлу2 >" в проекте "\<имя_проекта2 >".</span><span class="sxs-lookup"><span data-stu-id="f0167-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="f0167-105">Если обе сборки идентичны, попробуйте заменить эти ссылки так, чтобы они ссылались из одного места.</span><span class="sxs-lookup"><span data-stu-id="f0167-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="f0167-106">В случае, когда проект делает более одной ссылки на сборки компилятор не гарантирует, что одного типа могут преобразовываться в другой.</span><span class="sxs-lookup"><span data-stu-id="f0167-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="f0167-107">Каждая ссылка на файл задает путь и имя файла для выходного файла проекта (обычно DLL-файла).</span><span class="sxs-lookup"><span data-stu-id="f0167-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="f0167-108">Компилятор не гарантирует, что выходные файлы поступают из одного источника, либо что они представляют та же версия той же сборки.</span><span class="sxs-lookup"><span data-stu-id="f0167-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="f0167-109">Таким образом он не может гарантировать, что типы в различные ссылки относятся к одному типу или даже в том, что один можно преобразовать в другой.</span><span class="sxs-lookup"><span data-stu-id="f0167-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="f0167-110">Можно использовать ссылку на один файл, если известно, что указанные сборки имеют одинаковый идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="f0167-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="f0167-111">*Удостоверение сборки* включает имя сборки, версию, открытый ключ (при его наличии), язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="f0167-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="f0167-112">Эти сведения уникально идентифицируют сборку.</span><span class="sxs-lookup"><span data-stu-id="f0167-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="f0167-113">**Идентификатор ошибки:** BC30961</span><span class="sxs-lookup"><span data-stu-id="f0167-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f0167-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f0167-114">To correct this error</span></span>  
  
-   <span data-ttu-id="f0167-115">Если указанные сборки имеют одинаковый идентификатор сборки, удалите или замените одну из ссылок на файл таким образом, что только одна ссылка на файл.</span><span class="sxs-lookup"><span data-stu-id="f0167-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="f0167-116">Если эти сборки имеют одинаковый идентификатор сборки, измените код, чтобы не пытается преобразовать тип в одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="f0167-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0167-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f0167-117">See Also</span></span>  
 [<span data-ttu-id="f0167-118">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0167-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="f0167-119">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="f0167-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 
