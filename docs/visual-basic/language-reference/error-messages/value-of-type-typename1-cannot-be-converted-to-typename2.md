---
title: "Значение типа &quot;&lt;typename1&gt;«невозможно преобразовать»&lt;typename2&gt;&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
dev_langs:
- VB
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
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
ms.openlocfilehash: 2fbe1550515d2b15a3e349392fc8d78812787ae4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a><span data-ttu-id="01664-102">Значение типа "&lt;typename1&gt;«невозможно преобразовать»&lt;typename2&gt;"</span><span class="sxs-lookup"><span data-stu-id="01664-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="01664-103">Значение типа "\<typename1 настроек" нельзя преобразовать в "\<typename2 настроек".</span><span class="sxs-lookup"><span data-stu-id="01664-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="01664-104">Несоответствие типов может быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку "\<assemblyname настроек".</span><span class="sxs-lookup"><span data-stu-id="01664-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="01664-105">Попробуйте заменить ссылку на файл "\<filepath настроек" в проекте "\<projectname1 настроек" со ссылкой на проект "\<projectname2 настроек".</span><span class="sxs-lookup"><span data-stu-id="01664-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="01664-106">В ситуации, когда проект делает ссылку на проект и ссылки на файл компилятор не может гарантировать, что один тип можно преобразовать в другой.</span><span class="sxs-lookup"><span data-stu-id="01664-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="01664-107">Следующий псевдокод иллюстрирует ситуацию, которая может вызвать эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="01664-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="01664-108">Проект `P1` делает косвенную ссылку проекта посредством проекта `P2` проект `P3`, а также прямые ссылки на файл `P3`.</span><span class="sxs-lookup"><span data-stu-id="01664-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="01664-109">Объявление `commonObject` использует ссылку на файл `P3`, тогда как вызов `P2.getCommonClass` использует ссылку на проект `P3`.</span><span class="sxs-lookup"><span data-stu-id="01664-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="01664-110">В этом случае проблема: ссылка на файл задает путь и имя файла для выходного файла `P3` (обычно p3.dll), а в ссылки проекта обозначают исходный проект (`P3`) по имени проекта.</span><span class="sxs-lookup"><span data-stu-id="01664-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="01664-111">По этой причине компилятор не может гарантировать, что тип `P3.commonClass` поступает из того же исходного кода через две различные ссылки.</span><span class="sxs-lookup"><span data-stu-id="01664-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="01664-112">Это обычно происходит, когда ссылка проекта и файловая ссылка смешиваются.</span><span class="sxs-lookup"><span data-stu-id="01664-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="01664-113">В предыдущем примере проблема может не возникать при `P1` сделать прямую ссылку проекта на `P3` вместо ссылки на файл.</span><span class="sxs-lookup"><span data-stu-id="01664-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="01664-114">**Идентификатор ошибки:** BC30955</span><span class="sxs-lookup"><span data-stu-id="01664-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01664-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="01664-115">To correct this error</span></span>  
  
-   <span data-ttu-id="01664-116">Измените ссылку на файл ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="01664-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01664-117">См. также</span><span class="sxs-lookup"><span data-stu-id="01664-117">See Also</span></span>  
 <span data-ttu-id="01664-118">[Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="01664-118">[Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="01664-119"> [Управление ссылками проекта](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="01664-119"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="01664-120"> [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылки"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span><span class="sxs-lookup"><span data-stu-id="01664-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span></span>
