---
title: Директива x:Subclass
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
caps.latest.revision: 20
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 566b772db0e8f96c3272481d47b3e220f727d95b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="xsubclass-directive"></a><span data-ttu-id="a4bd3-102">Директива x:Subclass</span><span class="sxs-lookup"><span data-stu-id="a4bd3-102">x:Subclass Directive</span></span>
<span data-ttu-id="a4bd3-103">Изменяет поведение компиляции разметки XAML при `x:Class` также предоставляется.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="a4bd3-104">Вместо создания разделяемого класса, который основан на `x:Class`, предоставленный `x:Class` создается в качестве промежуточного класса, и затем предоставленный производный класс должен быть основан на `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a4bd3-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="a4bd3-105">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a4bd3-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="a4bd3-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`namespace`|<span data-ttu-id="a4bd3-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-107">Optional.</span></span> <span data-ttu-id="a4bd3-108">Указывает пространство имен CLR, который содержит `classname`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="a4bd3-109">Если `namespace` указан, точка (.) отделяет `namespace` и `classname`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|  
|`classname`|<span data-ttu-id="a4bd3-110">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-110">Required.</span></span> <span data-ttu-id="a4bd3-111">Указывает имя CLR разделяемого класса, который соединяет загруженный XAML и вашего кода программной части для этого кода XAML.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="a4bd3-112">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-112">See Remarks.</span></span>|  
|`subclassNamespace`|<span data-ttu-id="a4bd3-113">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-113">Optional.</span></span> <span data-ttu-id="a4bd3-114">Может отличаться от `namespace` если каждое пространство имен можно заменить другим.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="a4bd3-115">Указывает пространство имен CLR, который содержит `subclassName`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="a4bd3-116">Если `subclassName` указан, точка (.) отделяет `subclassNamespace` и `subclassName`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|  
|`subclassName`|<span data-ttu-id="a4bd3-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-117">Required.</span></span> <span data-ttu-id="a4bd3-118">Задает имя подкласса CLR.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-118">Specifies the CLR name of the subclass.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="a4bd3-119">Зависимости</span><span class="sxs-lookup"><span data-stu-id="a4bd3-119">Dependencies</span></span>  
 <span data-ttu-id="a4bd3-120">[Директива x: Class](../../../docs/framework/xaml-services/x-class-directive.md) также должен быть предоставлен в тот же объект, и этот объект должен быть корневым элементом рабочей среды XAML.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-120">[x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4bd3-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="a4bd3-121">Remarks</span></span>  
 <span data-ttu-id="a4bd3-122">`x:Subclass` Использование в первую очередь предназначена для языков, которые не поддерживают объявление разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>  
  
 <span data-ttu-id="a4bd3-123">Класс, используемый как `x:Subclass` не может быть вложенным классом и `x:Subclass` должен ссылаться на корневой объект, как описано в разделе «Зависимости».</span><span class="sxs-lookup"><span data-stu-id="a4bd3-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>  
  
 <span data-ttu-id="a4bd3-124">В противном случае концептуальное значение `x:Subclass` не определено в реализации служб XAML .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET Framework XAML Services implementation.</span></span> <span data-ttu-id="a4bd3-125">Это так, как поведение служб XAML .NET Framework не указывает общую модель программирования, которая разметки и вспомогательного кода являются подключения XAML.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-125">This is because .NET Framework XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="a4bd3-126">Реализации дополнительных понятий, связанных с `x:Class` и `x:Subclass` выполняются с конкретными платформами, которые используют модели программирования или модели приложений для определения способа соединения разметки XAML, скомпилированный разметки и на основе CLR кода.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="a4bd3-127">Каждая платформа может иметь собственные действия построения, включающие некоторое поведение или отдельные компоненты, которые должны быть включены в среде построения.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="a4bd3-128">Внутри платформы действия построения можно также различаются в зависимости от конкретного языка среды CLR, который используется для кода.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="a4bd3-129">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="a4bd3-129">WPF Usage Notes</span></span>  
 <span data-ttu-id="a4bd3-130">`x:Subclass` может быть на корневой страницы либо в <xref:System.Windows.Application> корневой в определении приложения, который уже имеет `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="a4bd3-131">Объявление `x:Subclass` на любой элемент, отличный от корня приложения или страницы и задания его там, где нет `x:Class` существует, приводит к ошибке времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>  
  
 <span data-ttu-id="a4bd3-132">Создание производных классов, правильно работающих `x:Subclass` сценария является довольно сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="a4bd3-133">Может потребоваться проверка промежуточных файлов (g-файлы в папке «obj» проекта путем компиляции разметки, с именами, включающими имена файлов).</span><span class="sxs-lookup"><span data-stu-id="a4bd3-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="a4bd3-134">Промежуточные файлы, которые могут помочь определить происхождение отдельных программных конструкций в разделяемых классах в скомпилированном приложении.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>  
  
 <span data-ttu-id="a4bd3-135">Обработчики событий в производном классе должен быть `internal override` (`Friend Overrides` в Visual Basic), чтобы переопределить заглушки для обработчиков, созданный в промежуточный класс во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in Microsoft Visual Basic) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="a4bd3-136">В противном случае реализация производного класса скрыть (тень) реализацию промежуточного класса и промежуточный класс обработчики не вызываются.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>  
  
 <span data-ttu-id="a4bd3-137">При определении обоих `x:Class` и `x:Subclass`, необходимо обеспечить реализацию для класса, на который ссылается `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="a4bd3-138">Необходимо присвоить ему имя через `x:Class` таким образом, чтобы у компилятора имеются некоторые рекомендации для класса, он создает в промежуточных файлов (компилятор не выбирает имя по умолчанию в данном случае).</span><span class="sxs-lookup"><span data-stu-id="a4bd3-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="a4bd3-139">Можно дать `x:Class` реализации класса; Однако это не типичный сценарий для использования обоих `x:Class` и `x:Subclass`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4bd3-140">См. также</span><span class="sxs-lookup"><span data-stu-id="a4bd3-140">See Also</span></span>  
 [<span data-ttu-id="a4bd3-141">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="a4bd3-141">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="a4bd3-142">Код XAML и пользовательские классы для WPF</span><span class="sxs-lookup"><span data-stu-id="a4bd3-142">XAML and Custom Classes for WPF</span></span>](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
