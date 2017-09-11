---
title: "Значение типа &quot;&lt;typename1&gt;«невозможно преобразовать»&lt;typename2&gt;&quot; (множественные ссылки на файл) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
dev_langs:
- VB
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
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
ms.openlocfilehash: 299cc4bec00a4597a661c5da49135fe3b5357537
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="e4ce6-102">Значение типа "&lt;typename1&gt;«невозможно преобразовать»&lt;typename2&gt;" (множественные ссылки на файл)</span><span class="sxs-lookup"><span data-stu-id="e4ce6-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="e4ce6-103">Значение типа "\<typename1 настроек" нельзя преобразовать в "\<typename2 настроек".</span><span class="sxs-lookup"><span data-stu-id="e4ce6-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="e4ce6-104">Несоответствие типов может быть вызвана смешением ссылки на файл "\<filepath1 настроек" в проекте "\<projectname1 настроек" со ссылкой на файл "\<filepath2 настроек" в проекте "\<projectname2 настроек".</span><span class="sxs-lookup"><span data-stu-id="e4ce6-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="e4ce6-105">Если обе сборки идентичны, попробуйте заменить эти ссылки так, чтобы они ссылались из одного места.</span><span class="sxs-lookup"><span data-stu-id="e4ce6-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="e4ce6-106">В ситуации, когда проект делает более одной ссылки на сборку компилятор не может гарантировать, что один тип можно преобразовать в другой.</span><span class="sxs-lookup"><span data-stu-id="e4ce6-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="e4ce6-107">Каждая ссылка на файл задает путь и имя файла для выходного файла проекта (как правило, файл DLL).</span><span class="sxs-lookup"><span data-stu-id="e4ce6-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="e4ce6-108">Компилятор не может гарантировать, что выходные файлы будут взяты из одного источника, либо что они представляют та же версия той же сборки.</span><span class="sxs-lookup"><span data-stu-id="e4ce6-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="e4ce6-109">Таким образом он не может гарантировать, что типы в различных ссылках относятся к одному типу, или даже что один можно преобразовать в другой.</span><span class="sxs-lookup"><span data-stu-id="e4ce6-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="e4ce6-110">Если вы знаете, что указанные сборки имеют одинаковый идентификатор сборки можно использовать ссылку на один файл.</span><span class="sxs-lookup"><span data-stu-id="e4ce6-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="e4ce6-111">*Удостоверение сборки* включает имя сборки, версию, открытый ключ (при его наличии), язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="e4ce6-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="e4ce6-112">Эти сведения уникально идентифицируют сборку.</span><span class="sxs-lookup"><span data-stu-id="e4ce6-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="e4ce6-113">**Идентификатор ошибки:** BC30961</span><span class="sxs-lookup"><span data-stu-id="e4ce6-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e4ce6-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e4ce6-114">To correct this error</span></span>  
  
-   <span data-ttu-id="e4ce6-115">Если указанные сборки имеют одинаковый идентификатор сборки, затем удалите или замените одну из ссылок на файл таким образом, что только одна ссылка на файл.</span><span class="sxs-lookup"><span data-stu-id="e4ce6-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="e4ce6-116">Если указанные сборки не имеют одинаковый идентификатор сборки, измените код, чтобы он пытался выполнить преобразование одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="e4ce6-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4ce6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e4ce6-117">See Also</span></span>  
 <span data-ttu-id="e4ce6-118">[Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="e4ce6-118">[Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="e4ce6-119"> [Управление ссылками проекта](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="e4ce6-119"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="e4ce6-120"> [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылки"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span><span class="sxs-lookup"><span data-stu-id="e4ce6-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span></span>
