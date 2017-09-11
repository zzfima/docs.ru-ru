---
title: "Это приложение с одним экземпляром не удалось подключиться к исходному экземпляру | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 113923e7cb72d1da0a8fb289f29e9afa60dda558
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="1e162-102">Данное приложение, допускающее только один экземпляр, не может подключиться к первоначальному экземпляру</span><span class="sxs-lookup"><span data-stu-id="1e162-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="1e162-103">Данное приложение, допускающее только один экземпляр, не может подключиться к первоначальному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="1e162-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="1e162-104">Вот некоторые возможные причины этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="1e162-104">Some of the possible causes for this problem are as follows:</span></span>  
  
-   <span data-ttu-id="1e162-105">Исходный экземпляр перестал отвечать.</span><span class="sxs-lookup"><span data-stu-id="1e162-105">The original instance stopped responding.</span></span>  
  
-   <span data-ttu-id="1e162-106">Приложение не имеет разрешений на создание объектов ядра.</span><span class="sxs-lookup"><span data-stu-id="1e162-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="1e162-107">Дополнительные сведения об объектах ядра см. в разделе [мьютексы](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).</span><span class="sxs-lookup"><span data-stu-id="1e162-107">For more information about kernel objects, see [Mutexes](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).</span></span>  
  
     <span data-ttu-id="1e162-108">Базовое имя для объектов ядра получается из последовательного объединения GUID сборки, основного номера версии и дополнительного номера версии.</span><span class="sxs-lookup"><span data-stu-id="1e162-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="1e162-109">Например, базовое имя может быть `3639f15d-9547-43da-8145-60da347829915.1`.</span><span class="sxs-lookup"><span data-stu-id="1e162-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="1e162-110">Исправление этой ошибки при разработке приложения</span><span class="sxs-lookup"><span data-stu-id="1e162-110">To correct this error when developing the application</span></span>  
  
1.  <span data-ttu-id="1e162-111">Проверьте, не переходит ли приложение в состояние, в котором оно не отвечает на запросы.</span><span class="sxs-lookup"><span data-stu-id="1e162-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2.  <span data-ttu-id="1e162-112">Убедитесь в том, что приложение имеет достаточно разрешений на создание объектов ядра.</span><span class="sxs-lookup"><span data-stu-id="1e162-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3.  <span data-ttu-id="1e162-113">Перезапустите исходный экземпляр приложения.</span><span class="sxs-lookup"><span data-stu-id="1e162-113">Restart the original instance of the application.</span></span>  
  
4.  <span data-ttu-id="1e162-114">Перезагрузите компьютер, чтобы удалить все процессы, которые могут использовать ресурсы, необходимые приложению для подключения к исходному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="1e162-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5.  <span data-ttu-id="1e162-115">Задокументируйте обстоятельства возникновения ошибки и обратитесь в службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1e162-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e162-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1e162-116">See Also</span></span>  
 <span data-ttu-id="1e162-117">[NIB: Как: Укажите поведение создания экземпляров приложения (Visual Basic)](http://msdn.microsoft.com/en-us/48539ad8-d960-4210-beab-ee65f6c6dc6e) </span><span class="sxs-lookup"><span data-stu-id="1e162-117">[NIB: How to: Specify Instancing Behavior for an Application (Visual Basic)](http://msdn.microsoft.com/en-us/48539ad8-d960-4210-beab-ee65f6c6dc6e) </span></span>  
<span data-ttu-id="1e162-118"> [Основы отладчика](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span><span class="sxs-lookup"><span data-stu-id="1e162-118"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span></span>  
<span data-ttu-id="1e162-119"> [PAVEOVER поддержка и продукта специальные возможности](http://msdn.microsoft.com/en-us/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)</span><span class="sxs-lookup"><span data-stu-id="1e162-119"> [PAVEOVER Product Support and Accessibility](http://msdn.microsoft.com/en-us/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)</span></span>
