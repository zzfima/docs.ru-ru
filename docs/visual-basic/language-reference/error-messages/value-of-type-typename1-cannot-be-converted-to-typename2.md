---
title: Значение типа <typename1> невозможно привести к <typename2>
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 5f313a43bc3a2f983dabbd45477d120fdb80d063
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766809"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a><span data-ttu-id="83a27-102">Значение типа "\<Имя_типа1 >" нельзя преобразовать в "\<имя_типа2 >"</span><span class="sxs-lookup"><span data-stu-id="83a27-102">Value of type '\<typename1>' cannot be converted to '\<typename2>'</span></span>
<span data-ttu-id="83a27-103">Значение типа "\<Имя_типа1 >" нельзя преобразовать в "\<имя_типа2 >".</span><span class="sxs-lookup"><span data-stu-id="83a27-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="83a27-104">Несоответствие типов может быть вызвана смешением ссылки на файл в проект ссылку на сборку "\<имя_сборки >".</span><span class="sxs-lookup"><span data-stu-id="83a27-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="83a27-105">Попробуйте заменить ссылку на файл "\<filepath >" в проекте "\<имя_проекта1 >" со ссылкой проекта "\<имя_проекта2 >".</span><span class="sxs-lookup"><span data-stu-id="83a27-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="83a27-106">В ситуации, когда проект делает ссылку на проект и ссылку на файл компилятор не может гарантировать, что один тип может быть преобразован в другой.</span><span class="sxs-lookup"><span data-stu-id="83a27-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="83a27-107">Следующий псевдокод иллюстрирует ситуацию, которая может вызвать эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="83a27-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
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
  
 <span data-ttu-id="83a27-108">Проект `P1` делает косвенную ссылку проекта через проект `P2` проект `P3`, а также прямые ссылки на файл `P3`.</span><span class="sxs-lookup"><span data-stu-id="83a27-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="83a27-109">Объявление `commonObject` использует ссылку на файл `P3`, тогда как вызов `P2.getCommonClass` использует ссылку на проект `P3`.</span><span class="sxs-lookup"><span data-stu-id="83a27-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="83a27-110">В этой ситуации проблема в том, что ссылка на файл задает путь к файлу и имя выходного файла `P3` (обычно p3.dll), хотя в проект ссылку на определение исходного проекта (`P3`) по имени проекта.</span><span class="sxs-lookup"><span data-stu-id="83a27-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="83a27-111">По этой причине компилятор не может гарантировать, что тип `P3.commonClass` поступает из того же исходного кода через две различные ссылки.</span><span class="sxs-lookup"><span data-stu-id="83a27-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="83a27-112">Такая ситуация обычно возникает, когда ссылка проекта и используются переменные типов ссылок на файлы.</span><span class="sxs-lookup"><span data-stu-id="83a27-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="83a27-113">В предыдущем примере, может не происходить, если `P1` сделать прямую ссылку проекта на `P3` вместо ссылки на файл.</span><span class="sxs-lookup"><span data-stu-id="83a27-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="83a27-114">**Идентификатор ошибки:** BC30955</span><span class="sxs-lookup"><span data-stu-id="83a27-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="83a27-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="83a27-115">To correct this error</span></span>  
  
- <span data-ttu-id="83a27-116">Измените ссылку на файл для ссылки на проект.</span><span class="sxs-lookup"><span data-stu-id="83a27-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a27-117">См. также</span><span class="sxs-lookup"><span data-stu-id="83a27-117">See also</span></span>

- [<span data-ttu-id="83a27-118">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83a27-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="83a27-119">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="83a27-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
