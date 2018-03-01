---
title: "Данное приложение, допускающее только один экземпляр, не может подключиться к первоначальному экземпляру"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9cb8cef696ba93f922dfe0d92195a5fb5147b4cc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="b12ae-102">Данное приложение, допускающее только один экземпляр, не может подключиться к первоначальному экземпляру</span><span class="sxs-lookup"><span data-stu-id="b12ae-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="b12ae-103">Данное приложение, допускающее только один экземпляр, не может подключиться к первоначальному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="b12ae-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="b12ae-104">Вот некоторые возможные причины этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="b12ae-104">Some of the possible causes for this problem are as follows:</span></span>  
  
-   <span data-ttu-id="b12ae-105">Исходный экземпляр перестал отвечать.</span><span class="sxs-lookup"><span data-stu-id="b12ae-105">The original instance stopped responding.</span></span>  
  
-   <span data-ttu-id="b12ae-106">Приложение не имеет разрешений на создание объектов ядра.</span><span class="sxs-lookup"><span data-stu-id="b12ae-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="b12ae-107">Дополнительные сведения об объектах ядра см. в разделе [мьютексы](../../standard/threading/mutexes.md).</span><span class="sxs-lookup"><span data-stu-id="b12ae-107">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="b12ae-108">Базовое имя для объектов ядра получается из последовательного объединения GUID сборки, основного номера версии и дополнительного номера версии.</span><span class="sxs-lookup"><span data-stu-id="b12ae-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="b12ae-109">Например, базовое имя может быть `3639f15d-9547-43da-8145-60da347829915.1`.</span><span class="sxs-lookup"><span data-stu-id="b12ae-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="b12ae-110">Исправление этой ошибки при разработке приложения</span><span class="sxs-lookup"><span data-stu-id="b12ae-110">To correct this error when developing the application</span></span>  
  
1.  <span data-ttu-id="b12ae-111">Проверьте, не переходит ли приложение в состояние, в котором оно не отвечает на запросы.</span><span class="sxs-lookup"><span data-stu-id="b12ae-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2.  <span data-ttu-id="b12ae-112">Убедитесь в том, что приложение имеет достаточно разрешений на создание объектов ядра.</span><span class="sxs-lookup"><span data-stu-id="b12ae-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3.  <span data-ttu-id="b12ae-113">Перезапустите исходный экземпляр приложения.</span><span class="sxs-lookup"><span data-stu-id="b12ae-113">Restart the original instance of the application.</span></span>  
  
4.  <span data-ttu-id="b12ae-114">Перезагрузите компьютер, чтобы удалить все процессы, которые могут использовать ресурсы, необходимые приложению для подключения к исходному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="b12ae-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5.  <span data-ttu-id="b12ae-115">Задокументируйте обстоятельства возникновения ошибки и обратитесь в службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b12ae-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12ae-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b12ae-116">See Also</span></span>  
 [<span data-ttu-id="b12ae-117">Основы отладки</span><span class="sxs-lookup"><span data-stu-id="b12ae-117">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)  

