---
title: "Обработка заказов с помощью политики"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66833724-dc36-4fad-86b0-59ffeaa3ba6a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b479e6129cc5ba158549294acf25d4b8f71a3ff4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="order-processing-with-policy"></a><span data-ttu-id="5c5e6-102">Обработка заказов с помощью политики</span><span class="sxs-lookup"><span data-stu-id="5c5e6-102">Order Processing with Policy</span></span>
<span data-ttu-id="5c5e6-103">В данном образце политики обработки заказов продемонстрированы некоторые ключевые функции, представленные в [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] платформы Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="5c5e6-103">The Order Processing Policy sample demonstrates some of the key features introduced in the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] of the Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="5c5e6-104">В обработчике правил WF реализованы следующие новые функции:</span><span class="sxs-lookup"><span data-stu-id="5c5e6-104">The following functionality is new for the WF rules engine:</span></span>  
  
-   <span data-ttu-id="5c5e6-105">поддержка перегрузки операторов;</span><span class="sxs-lookup"><span data-stu-id="5c5e6-105">Support for operator overloading.</span></span>  
  
-   <span data-ttu-id="5c5e6-106">поддержка оператора `new`, который позволяет пользователям создавать новые объекты и массивы из правил WF;</span><span class="sxs-lookup"><span data-stu-id="5c5e6-106">Support for the `new` operator, allowing users to create new objects and arrays from WF rules.</span></span>  
  
-   <span data-ttu-id="5c5e6-107">поддержка методов расширения, которые обеспечивают совместимость пользовательских вызовов методов расширения из WF со стилями программирования С#.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-107">Support for extension methods to make the user experience in calling extension methods from WF rules compatible with C# coding styles.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c5e6-108">Для этого образца необходимо установить, выполнить сборку и запустить [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c5e6-108">This sample requires that [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] is installed to build and run.</span></span> [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]<span data-ttu-id="5c5e6-109"> необходимо, чтобы открыть файлы проекта и решения.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-109"> is required to open the project and solution files.</span></span>  
  
 <span data-ttu-id="5c5e6-110">В данном образце демонстрируется проект `OrderProcessingPolicy`, в котором вводится заказ клиента, состоящий из нумерованного списка доступных элементов и почтового индекса.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-110">The sample demonstrates an `OrderProcessingPolicy` project in which a customer order, which consists of a numbered list of available items and a zip code, is entered.</span></span> <span data-ttu-id="5c5e6-111">Обработка заказа выполняется успешно, если обе записи верны, в противном случае политика создает объекты ошибок, используя перегруженный оператор `+` и предварительно определенный метод расширения, чтобы информировать пользователей об ошибках.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-111">The order is processed successfully if both entries are correct; otherwise, the policy creates error objects, utilizing an overloaded `+` operator and a predefined extension method to inform the user of the errors.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5c5e6-112">методах расширения см. в разделе [спецификация C# версии 3.0](http://go.microsoft.com/fwlink/?LinkId=95402).</span><span class="sxs-lookup"><span data-stu-id="5c5e6-112"> extension methods, see [C# Version 3.0 Specification](http://go.microsoft.com/fwlink/?LinkId=95402).</span></span>  
  
 <span data-ttu-id="5c5e6-113">Образец включает следующие проекты:</span><span class="sxs-lookup"><span data-stu-id="5c5e6-113">The sample is comprised of the following projects:</span></span>  
  
-   `OrderErrorLibrary`  
  
     <span data-ttu-id="5c5e6-114">`OrderErrorLibrary` - библиотека классов, которая определяет классы `OrderError` и `OrderErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-114">The `OrderErrorLibrary` is a class library that defines `OrderError` and `OrderErrorCollection` classes.</span></span> <span data-ttu-id="5c5e6-115">При неверном вводе создается экземпляр `OrderError`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-115">An `OrderError` instance is created when an invalid input is entered.</span></span> <span data-ttu-id="5c5e6-116">Библиотека также предоставляет методы расширения для класса `OrderErrorCollection`, который выдает свойство `ErrorText` для всех объектов `OrderError` в коллекции `OrderErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-116">The library also provides an extension method on the `OrderErrorCollection` class that outputs the `ErrorText` property on all `OrderError` objects in the `OrderErrorCollection`.</span></span>  
  
-   `OrderProcessingPolicy`  
  
     <span data-ttu-id="5c5e6-117">Проект `OrderProcessingPolicy` представляет собой консольное приложение WF, которое определяет одно действие `PolicyFromFile`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-117">The `OrderProcessingPolicy` project is a WF console application that defines a single `PolicyFromFile` activity.</span></span> <span data-ttu-id="5c5e6-118">В данном действии содержатся следующие правила:</span><span class="sxs-lookup"><span data-stu-id="5c5e6-118">The activity has the following rules:</span></span>  
  
    -   `invalidItemNum`  
  
         <span data-ttu-id="5c5e6-119">Данное правило проверяет, что элемент имеет номер от 1 до 6 включительно.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-119">This rule validates that the item number is between 1 and 6, inclusive.</span></span> <span data-ttu-id="5c5e6-120">Если номер элемента находится в пределах допустимого диапазона, правило ничего не делает (кроме печати в консоль).</span><span class="sxs-lookup"><span data-stu-id="5c5e6-120">If the item number is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="5c5e6-121">Если номер элемента находится вне диапазона 1-6, правило `invalidItemNum` выполняет перечисленные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-121">If the item number is not between 1 and 6, the `invalidItemNum` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="5c5e6-122">Создает новый объект `OrderError`, передавая ему заданный номер элемента, и устанавливает свойства `ErrorText` и `CustomerName` для объекта.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-122">Creates a new `OrderError` object, passing it the item number entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="5c5e6-123">Создает объект `invalidItemNumErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-123">Creates an `invalidItemNumErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="5c5e6-124">Добавляет новый экземпляр `OrderError` в коллекцию `invalidItemNumErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-124">Adds the newly-created `OrderError` instance to the `invalidItemNumErrorCollection`.</span></span>  
  
         <span data-ttu-id="5c5e6-125">Таким образом реализована функция поддержки оператора `new`, с помощью которого в правилах можно создавать экземпляры объектов.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-125">This demonstrates support for the `new` operator, with which you can instantiate objects inside rules.</span></span>  
  
    -   `invalidZip`  
  
         <span data-ttu-id="5c5e6-126">Это правило проверяет, что почтовый индекс содержит 5 цифр и находится в диапазоне от 600 до 99998.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-126">This rule validates that the zip code has 5 digits, and is within the range 600 to 99998.</span></span> <span data-ttu-id="5c5e6-127">Если почтовый индекс находится в пределах допустимого диапазона, правило ничего не делает (кроме печати в консоль).</span><span class="sxs-lookup"><span data-stu-id="5c5e6-127">If the zip code is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="5c5e6-128">Если длина почтового индекса меньше 5 цифр или индекс находится вне диапазона 00600–99998, правило `invalidZip` выполняет перечисленные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-128">If the length of the zip code is less than 5, or the zip code is not between 00600 and 99998, the `invalidZip` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="5c5e6-129">Создает объект `OrderError`, передавая ему заданный почтовый индекс, и устанавливает свойства `ErrorText` и `CustomerName` для объекта.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-129">Creates an `OrderError` object, passing it the zip code entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="5c5e6-130">Создает объект `invalidZipCodeErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-130">Creates an `invalidZipCodeErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="5c5e6-131">Добавляет новый экземпляр `OrderError` в новую коллекцию `invalidZipCodeErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-131">Adds the newly-created `OrderError` instance to the newly-created `invalidZipCodeErrorCollection`.</span></span>  
  
         <span data-ttu-id="5c5e6-132">Таким образом в данном правиле снова реализована функция поддержки оператора `new`, с помощью которого в правилах можно создавать экземпляры объектов.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-132">This rule again demonstrates support for the `new` operator, which allows you to instantiate objects inside rules.</span></span>  
  
    -   `displayErrors`  
  
         <span data-ttu-id="5c5e6-133">Это правило проверяет наличие ошибок, добавленных предыдущими двумя правилами в два объекта `OrderErrorCollection`: `invalidItemNumErrorCollection` и `invalidIZipCodeErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-133">This rule checks to see if there were any errors added by the previous two rules in the two `OrderErrorCollection` objects `invalidItemNumErrorCollection` and `invalidIZipCodeErrorCollection`.</span></span> <span data-ttu-id="5c5e6-134">При обнаружении ошибок (`invalidItemNumErrorCollection` или `invalidZipCodeErrorCollection` не равны `null`) правило выполняет перечисленные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-134">If there were errors (either `invalidItemNumErrorCollection` or `invalidZipCodeErrorCollection` is not `null`), the rule does the following:</span></span>  
  
        1.  <span data-ttu-id="5c5e6-135">Вызывает перегруженный `+` оператор, чтобы скопировать содержимое `invalidItemNumErrorCollection` и `invalidZipCodeErrorCollection` для `invalidOrdersCollection``OrderErrorCollection` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-135">Calls the overloaded `+` operator to copy the contents of `invalidItemNumErrorCollection` and `invalidZipCodeErrorCollection` to an `invalidOrdersCollection``OrderErrorCollection` instance.</span></span>  
  
        2.  <span data-ttu-id="5c5e6-136">Вызывает метод расширения `PrintOrderErrors` для коллекции `invalidOrdersCollection` и выдает свойство `ErrorText` для всех объектов `orderError` в коллекции `invalidOrdersCollection`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-136">Calls the `PrintOrderErrors` extension method on `invalidOrdersCollection` and outputs the `ErrorText` property on all `orderError` objects in `invalidOrdersCollection`.</span></span>  
  
 <span data-ttu-id="5c5e6-137">Перегруженный оператор `+` для объекта `OrderErrorCollection` определяется в классе `OrderErrorCollection` в проекте `OrderErrorLibrary`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-137">The overloaded operator `+` on the `OrderErrorCollection` is defined in the `OrderErrorCollection` class, in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="5c5e6-138">Он объединяет два объекта `OrderErrorCollection` в один объект `OrderErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-138">It takes two `OrderErrorCollection` objects and combines them into one `OrderErrorCollection` object.</span></span>  
  
 <span data-ttu-id="5c5e6-139">Метод расширения `PrintOrderErrors` также определяется в проекте `OrderErrorLibrary`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-139">The `PrintOrderErrors` extension method is also defined in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="5c5e6-140">Методы расширения являются новой функциональной возможностью С#, которая позволяет разработчикам добавлять новые методы в открытый контракт существующего CLR-типа без необходимости создавать класс, производный от данного типа, или повторно компилировать исходный тип.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-140">Extension methods are a new C# feature that enables developers to add new methods to the public contract of an existing CLR type, without having to derive a class from it or recompile the original type.</span></span>  
  
 <span data-ttu-id="5c5e6-141">При выполнении образца запрашивается ввод имени, номер приобретаемого товара и почтовый индекс.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-141">When you run the sample you are prompted to enter a name, the item number of the item to be purchased, and a zip code.</span></span> <span data-ttu-id="5c5e6-142">Эти данные затем проверяются правилами, определенными в данном действии политики.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-142">This information is then verified by the rules defined in the policy activity.</span></span> <span data-ttu-id="5c5e6-143">В следующем образце демонстрируется результат действия данной программы.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-143">The following is sample output from the program.</span></span>  
  
```  
Please enter your name: John  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 1  
  
Please enter your 5-Digit zip code: 98102  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Thank you for your order, it has been processed.  
  
Workflow Completed  
Another Order? (Y/N): y  
  
Please enter your name: Joel  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 8  
  
Please enter your 5-Digit zip code: 0000  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Your order contains the following error(s)  
  
Error: No item number found. Please choose an available item.  
Error: Invalid zip code. Please choose a zip code between 00600 and 99998.  
  
Workflow Completed  
Another Order? (Y/N): n  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5c5e6-144">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="5c5e6-144">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5c5e6-145">Откройте файл проекта "OrderProcessingPolicy.sln" в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c5e6-145">Open the OrderProcessingPolicy.sln project file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="5c5e6-146">В данном решении находятся два различных проекта: `OrderErrorLibrary` и `OrderProcessingPolicy`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-146">There are two different projects in the solution: `OrderErrorLibrary` and `OrderProcessingPolicy`.</span></span> <span data-ttu-id="5c5e6-147">Проект `OrderProcessingPolicy` использует классы и методы, определенные в `OrderErrorLibrary`.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-147">The `OrderProcessingPolicy` project uses classes and methods defined in the `OrderErrorLibrary`.</span></span>  
  
3.  <span data-ttu-id="5c5e6-148">Выполните построение всех проектов.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-148">Build all projects.</span></span>  
  
4.  <span data-ttu-id="5c5e6-149">Щелкните **Запуск**.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-149">Click **Run**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5c5e6-150">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5c5e6-150">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5c5e6-151">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5c5e6-151">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5c5e6-152">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c5e6-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5c5e6-153">Этот образец находится в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="5c5e6-153">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\OrderProcessingPolicy`  
  
## <a name="see-also"></a><span data-ttu-id="5c5e6-154">См. также</span><span class="sxs-lookup"><span data-stu-id="5c5e6-154">See Also</span></span>
