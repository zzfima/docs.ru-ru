---
title: Объект My.WebServices
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9f2c4017a1df8059f2cc57e7c30a96c474cfda0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="mywebservices-object"></a><span data-ttu-id="91766-102">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="91766-102">My.WebServices Object</span></span>
<span data-ttu-id="91766-103">Предоставляет свойства для создания и доступа к один экземпляр каждого веб-службы XML ссылается текущий проект.</span><span class="sxs-lookup"><span data-stu-id="91766-103">Provides properties for creating and accessing a single instance of each XML Web service referenced by the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91766-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="91766-104">Remarks</span></span>  
 <span data-ttu-id="91766-105">Объект `My.WebServices` предоставляет экземпляр каждой веб-службы, на которую ссылается текущий проект.</span><span class="sxs-lookup"><span data-stu-id="91766-105">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="91766-106">Каждый экземпляр создается по запросу.</span><span class="sxs-lookup"><span data-stu-id="91766-106">Each instance is instantiated on demand.</span></span> <span data-ttu-id="91766-107">Доступ к этим веб-службам можно получить через свойства объекта `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="91766-107">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="91766-108">Имя свойства совпадает с именем веб-службы, к которой обращается свойство.</span><span class="sxs-lookup"><span data-stu-id="91766-108">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="91766-109">Любой класс, наследуемый от <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>, является веб-службой.</span><span class="sxs-lookup"><span data-stu-id="91766-109">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span> <span data-ttu-id="91766-110">Сведения о добавлении веб-служб в проект см. в разделе [доступ к веб-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="91766-110">For information about adding Web services to a project, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="91766-111">`My.WebServices` Объект предоставляет только веб-службы, связанный с текущим проектом.</span><span class="sxs-lookup"><span data-stu-id="91766-111">The `My.WebServices` object exposes only the Web services associated with the current project.</span></span> <span data-ttu-id="91766-112">Он не предоставляет доступ к веб-службам, объявленным в присоединенных DLL.</span><span class="sxs-lookup"><span data-stu-id="91766-112">It does not provide access to Web services declared in referenced DLLs.</span></span> <span data-ttu-id="91766-113">Для доступа к веб-службу, которая предоставляет библиотеку DLL, необходимо использовать полное имя веб-службы в виде *DllName*. *ИмяВебСлужбы*.</span><span class="sxs-lookup"><span data-stu-id="91766-113">To access a Web service that a DLL provides, you must use the qualified name of the Web service, in the form *DllName*.*WebServiceName*.</span></span> <span data-ttu-id="91766-114">Дополнительные сведения см. в разделе [доступ к веб-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="91766-114">For more information, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="91766-115">Объект и его свойства недоступны для веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="91766-115">The object and its properties are not available for Web applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="91766-116">Свойства</span><span class="sxs-lookup"><span data-stu-id="91766-116">Properties</span></span>  
 <span data-ttu-id="91766-117">Каждое свойство `My.WebServices` объект предоставляет доступ к экземпляру веб-службы, на которые имеются ссылки в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="91766-117">Each property of the `My.WebServices` object provides access to an instance of a Web service referenced by the current project.</span></span> <span data-ttu-id="91766-118">Имя свойства совпадает с именем веб-службы, который обращается к свойству, а тип свойства совпадает с типом веб-службы.</span><span class="sxs-lookup"><span data-stu-id="91766-118">The name of the property is the same as the name of the Web service that the property accesses, and the property type is the same as the Web service's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91766-119">Если имеется конфликт имен, имя свойства для доступа к веб-службы является *RootNamespace*_*имен*\_*ServiceName*.</span><span class="sxs-lookup"><span data-stu-id="91766-119">If there is a name collision, the property name for accessing a Web service is *RootNamespace*_*Namespace*\_*ServiceName*.</span></span> <span data-ttu-id="91766-120">Например, рассмотрим две веб-службы с именем `Service1`.</span><span class="sxs-lookup"><span data-stu-id="91766-120">For example, consider two Web services named `Service1`.</span></span> <span data-ttu-id="91766-121">Если один из этих служб находится в корневом пространстве имен `WindowsApplication1` и в пространстве имен `Namespace1`, доступ к этой службе с помощью `My.WebServices.WindowsApplication1_Namespace1_Service1`.</span><span class="sxs-lookup"><span data-stu-id="91766-121">If one of these services is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that service by using `My.WebServices.WindowsApplication1_Namespace1_Service1`.</span></span>  
  
 <span data-ttu-id="91766-122">При первом обращении к одной из `My.WebServices` свойств объекта, он создает новый экземпляр веб-службы и сохраняет его.</span><span class="sxs-lookup"><span data-stu-id="91766-122">When you first access one of the `My.WebServices` object's properties, it creates a new instance of the Web service and stores it.</span></span> <span data-ttu-id="91766-123">Последующие обращения к этим свойствам возвращают этот экземпляр веб-службы.</span><span class="sxs-lookup"><span data-stu-id="91766-123">Subsequent accesses of that property return that instance of the Web service.</span></span>  
  
 <span data-ttu-id="91766-124">Веб-службы можно освободить путем назначения `Nothing` свойства для этой веб-службы.</span><span class="sxs-lookup"><span data-stu-id="91766-124">You can dispose of a Web service by assigning `Nothing` to the property for that Web service.</span></span> <span data-ttu-id="91766-125">Метод задания свойства назначает `Nothing` с сохраненным значением.</span><span class="sxs-lookup"><span data-stu-id="91766-125">The property setter assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="91766-126">Если присвоить любое значение, отличное от `Nothing` к свойству, методу задания создает исключение <xref:System.ArgumentException> исключение.</span><span class="sxs-lookup"><span data-stu-id="91766-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="91766-127">Можно проверить, является ли свойство `My.WebServices` объект сохраняет экземпляр веб-службы с помощью `Is` или `IsNot` оператор.</span><span class="sxs-lookup"><span data-stu-id="91766-127">You can test whether a property of the `My.WebServices` object stores an instance of the Web service by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="91766-128">Эти операторы можно использовать для проверки, если значение свойства `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="91766-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91766-129">Как правило `Is` или `IsNot` оператор имеет считывается значение свойства для выполнения сравнения.</span><span class="sxs-lookup"><span data-stu-id="91766-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="91766-130">Тем не менее если в настоящее время хранит свойство `Nothing`, свойство создает новый экземпляр веб-службы и затем возвращает этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="91766-130">However, if the property currently stores `Nothing`, the property creates a new instance of the Web service and then returns that instance.</span></span> <span data-ttu-id="91766-131">Однако компилятор Visual Basic обрабатывает свойства `My.WebServices` специально объекта и позволяет `Is` или `IsNot` проверить состояние свойства без изменения его значения.</span><span class="sxs-lookup"><span data-stu-id="91766-131">However, the Visual Basic compiler treats the properties of the `My.WebServices` object specially, and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91766-132">Пример</span><span class="sxs-lookup"><span data-stu-id="91766-132">Example</span></span>  
 <span data-ttu-id="91766-133">В этом примере вызывается `FahrenheitToCelsius` метод `TemperatureConverter` веб-службы XML и возвращает результат.</span><span class="sxs-lookup"><span data-stu-id="91766-133">This example calls the `FahrenheitToCelsius` method of the `TemperatureConverter` XML Web service, and returns the result.</span></span>  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 <span data-ttu-id="91766-134">Для работы этого примера проект должен ссылаться на веб-службы с именем `Converter`, и должен предоставлять эту веб-службу `ConvertTemperature` метод.</span><span class="sxs-lookup"><span data-stu-id="91766-134">For this example to work, your project must reference a Web service named `Converter`, and that Web service must expose the `ConvertTemperature` method.</span></span> <span data-ttu-id="91766-135">Дополнительные сведения см. в разделе [доступ к веб-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="91766-135">For more information, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="91766-136">Этот код не работает в проект веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="91766-136">This code does not work in a Web application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91766-137">Требования</span><span class="sxs-lookup"><span data-stu-id="91766-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="91766-138">Доступность по типу проекта</span><span class="sxs-lookup"><span data-stu-id="91766-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="91766-139">Тип проекта</span><span class="sxs-lookup"><span data-stu-id="91766-139">Project type</span></span>|<span data-ttu-id="91766-140">Доступно</span><span class="sxs-lookup"><span data-stu-id="91766-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="91766-141">Приложение Windows</span><span class="sxs-lookup"><span data-stu-id="91766-141">Windows Application</span></span>|<span data-ttu-id="91766-142">**Да**</span><span class="sxs-lookup"><span data-stu-id="91766-142">**Yes**</span></span>|  
|<span data-ttu-id="91766-143">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="91766-143">Class Library</span></span>|<span data-ttu-id="91766-144">**Да**</span><span class="sxs-lookup"><span data-stu-id="91766-144">**Yes**</span></span>|  
|<span data-ttu-id="91766-145">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="91766-145">Console Application</span></span>|<span data-ttu-id="91766-146">**Да**</span><span class="sxs-lookup"><span data-stu-id="91766-146">**Yes**</span></span>|  
|<span data-ttu-id="91766-147">Библиотека элементов управления Windows</span><span class="sxs-lookup"><span data-stu-id="91766-147">Windows Control Library</span></span>|<span data-ttu-id="91766-148">**Да**</span><span class="sxs-lookup"><span data-stu-id="91766-148">**Yes**</span></span>|  
|<span data-ttu-id="91766-149">Библиотека веб-элементов управления</span><span class="sxs-lookup"><span data-stu-id="91766-149">Web Control Library</span></span>|<span data-ttu-id="91766-150">**Да**</span><span class="sxs-lookup"><span data-stu-id="91766-150">**Yes**</span></span>|  
|<span data-ttu-id="91766-151">Служба Windows</span><span class="sxs-lookup"><span data-stu-id="91766-151">Windows Service</span></span>|<span data-ttu-id="91766-152">**Да**</span><span class="sxs-lookup"><span data-stu-id="91766-152">**Yes**</span></span>|  
|<span data-ttu-id="91766-153">Веб-сайт</span><span class="sxs-lookup"><span data-stu-id="91766-153">Web Site</span></span>|<span data-ttu-id="91766-154">Нет</span><span class="sxs-lookup"><span data-stu-id="91766-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91766-155">См. также</span><span class="sxs-lookup"><span data-stu-id="91766-155">See Also</span></span>  
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>  
 <xref:System.ArgumentException>  
 [<span data-ttu-id="91766-156">Доступ к веб-службам приложения</span><span class="sxs-lookup"><span data-stu-id="91766-156">Accessing Application Web Services</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
