---
title: Непредвиденная ошибка, так как операционная система не может получить ресурсы, требуемые для запуска одного экземпляра.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 9aa7ba0babe0a89942e320a76e07c05162b31700
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313616"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="fdd80-102">Непредвиденная ошибка, так как операционная система не может получить ресурсы, требуемые для запуска одного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="fdd80-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="fdd80-103">Приложению не удалось получить требуемый ресурс операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fdd80-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="fdd80-104">Вот некоторые возможные причины этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="fdd80-104">Some of the possible causes for this problem are:</span></span>  
  
-   <span data-ttu-id="fdd80-105">Приложение не имеет разрешений на создание именованных объектов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fdd80-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
-   <span data-ttu-id="fdd80-106">Среда CLR не имеет разрешений на создание размещенных в памяти файлов.</span><span class="sxs-lookup"><span data-stu-id="fdd80-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
-   <span data-ttu-id="fdd80-107">Приложению требуется доступ к объекту операционной системы, который используется другим процессом.</span><span class="sxs-lookup"><span data-stu-id="fdd80-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fdd80-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="fdd80-108">To correct this error</span></span>  
  
1. <span data-ttu-id="fdd80-109">Убедитесь, что у приложения достаточно прав на создание именованных объектов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fdd80-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2. <span data-ttu-id="fdd80-110">Убедитесь, что у среды CLR достаточно прав на создание размещенных в памяти файлов.</span><span class="sxs-lookup"><span data-stu-id="fdd80-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3. <span data-ttu-id="fdd80-111">Перезапустите компьютер, чтобы очистить все процессы, которые могут использовать ресурс, необходимый для подключения к приложению исходного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="fdd80-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4. <span data-ttu-id="fdd80-112">Запомните, при каких условиях произошла ошибка, и обратитесь в службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fdd80-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd80-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fdd80-113">See also</span></span>

- [<span data-ttu-id="fdd80-114">Application Page, Project Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdd80-114">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="fdd80-115">Основы отладки</span><span class="sxs-lookup"><span data-stu-id="fdd80-115">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
- [<span data-ttu-id="fdd80-116">Talk to Us</span><span class="sxs-lookup"><span data-stu-id="fdd80-116">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
