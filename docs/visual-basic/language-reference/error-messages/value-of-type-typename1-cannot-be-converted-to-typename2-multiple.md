---
title: "Значение типа &#39; &lt;Имя_типа1&gt;&#39; невозможно преобразовать в &#39;&lt; имя_типа2&gt;&#39; (Несколько ссылок на файлы)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords: BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc6138c7a7ca7d50a56fdd1f536e8d2dc3462a08
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="5c320-102">Значение типа &#39; &lt;Имя_типа1&gt;&#39; невозможно преобразовать в &#39;&lt; имя_типа2&gt;&#39; (Несколько ссылок на файлы)</span><span class="sxs-lookup"><span data-stu-id="5c320-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="5c320-103">Значение типа "\<Имя_типа1 >" нельзя преобразовать в "\<имя_типа2 >".</span><span class="sxs-lookup"><span data-stu-id="5c320-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="5c320-104">Несоответствие типов может быть вызвана смешением ссылки на файл "\<путь_к_файлу1 >" в проекте "\<имя_проекта1 >" со ссылкой на файл "\<путь_к_файлу2 >" в проекте "\<имя_проекта2 >".</span><span class="sxs-lookup"><span data-stu-id="5c320-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="5c320-105">Если обе сборки идентичны, попробуйте заменить эти ссылки так, чтобы они ссылались из одного места.</span><span class="sxs-lookup"><span data-stu-id="5c320-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="5c320-106">В случае, когда проект делает более одной ссылки на сборки компилятор не гарантирует, что одного типа могут преобразовываться в другой.</span><span class="sxs-lookup"><span data-stu-id="5c320-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="5c320-107">Каждая ссылка на файл задает путь и имя файла для выходного файла проекта (обычно DLL-файла).</span><span class="sxs-lookup"><span data-stu-id="5c320-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="5c320-108">Компилятор не гарантирует, что выходные файлы поступают из одного источника, либо что они представляют та же версия той же сборки.</span><span class="sxs-lookup"><span data-stu-id="5c320-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="5c320-109">Таким образом он не может гарантировать, что типы в различные ссылки относятся к одному типу или даже в том, что один можно преобразовать в другой.</span><span class="sxs-lookup"><span data-stu-id="5c320-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="5c320-110">Можно использовать ссылку на один файл, если известно, что указанные сборки имеют одинаковый идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="5c320-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="5c320-111">*Удостоверение сборки* включает имя сборки, версию, открытый ключ (при его наличии), язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="5c320-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="5c320-112">Эти сведения уникально идентифицируют сборку.</span><span class="sxs-lookup"><span data-stu-id="5c320-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="5c320-113">**Идентификатор ошибки:** BC30961</span><span class="sxs-lookup"><span data-stu-id="5c320-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5c320-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5c320-114">To correct this error</span></span>  
  
-   <span data-ttu-id="5c320-115">Если указанные сборки имеют одинаковый идентификатор сборки, удалите или замените одну из ссылок на файл таким образом, что только одна ссылка на файл.</span><span class="sxs-lookup"><span data-stu-id="5c320-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="5c320-116">Если эти сборки имеют одинаковый идентификатор сборки, измените код, чтобы не пытается преобразовать тип в одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="5c320-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c320-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5c320-117">See Also</span></span>  
 [<span data-ttu-id="5c320-118">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c320-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="5c320-119">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="5c320-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="5c320-120">NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылок"</span><span class="sxs-lookup"><span data-stu-id="5c320-120">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
