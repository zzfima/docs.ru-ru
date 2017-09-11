---
title: "Непредвиденная ошибка, так как ресурс операционной системы, необходимые для запуска одного экземпляра не может быть получена | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
dev_langs:
- VB
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: 10
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
ms.openlocfilehash: 03ab2d1c746fbc28c0c6f3e59371cc6bbd4050cd
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="12257-102">Непредвиденная ошибка, так как операционная система не может получить ресурсы, требуемые для запуска одного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="12257-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="12257-103">Приложению не удалось получить требуемый ресурс операционной системы.</span><span class="sxs-lookup"><span data-stu-id="12257-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="12257-104">Вот некоторые возможные причины этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="12257-104">Some of the possible causes for this problem are:</span></span>  
  
-   <span data-ttu-id="12257-105">Приложение не имеет разрешений на создание именованных объектов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="12257-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
-   <span data-ttu-id="12257-106">Среда CLR не имеет разрешений на создание размещенных в памяти файлов.</span><span class="sxs-lookup"><span data-stu-id="12257-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
-   <span data-ttu-id="12257-107">Приложению требуется доступ к объекту операционной системы, который используется другим процессом.</span><span class="sxs-lookup"><span data-stu-id="12257-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="12257-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="12257-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="12257-109">Убедитесь, что у приложения достаточно прав на создание именованных объектов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="12257-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2.  <span data-ttu-id="12257-110">Убедитесь, что у среды CLR достаточно прав на создание размещенных в памяти файлов.</span><span class="sxs-lookup"><span data-stu-id="12257-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3.  <span data-ttu-id="12257-111">Перезапустите компьютер, чтобы очистить все процессы, которые могут использовать ресурс, необходимый для подключения к приложению исходного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="12257-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4.  <span data-ttu-id="12257-112">Запомните, при каких условиях произошла ошибка, и обратитесь в службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="12257-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12257-113">См. также</span><span class="sxs-lookup"><span data-stu-id="12257-113">See Also</span></span>  
 <span data-ttu-id="12257-114">[Страница "Приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="12257-114">[Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="12257-115"> [Основы отладчика](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span><span class="sxs-lookup"><span data-stu-id="12257-115"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span></span>  
<span data-ttu-id="12257-116"> [Обращайтесь к нам](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="12257-116"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
