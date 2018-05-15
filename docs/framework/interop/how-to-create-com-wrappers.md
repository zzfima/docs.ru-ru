---
title: Практическое руководство. Создание оболочек COM
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4deb355a7b523437ae31a1d2b9c79e3b8d4f40a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="94741-102">Практическое руководство. Создание оболочек COM</span><span class="sxs-lookup"><span data-stu-id="94741-102">How to: Create COM Wrappers</span></span>
<span data-ttu-id="94741-103">Программы-оболочки модели COM можно создавать с использованием функций [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] или средств платформы .NET Framework (Tlbimp.exe и Regasm.exe).</span><span class="sxs-lookup"><span data-stu-id="94741-103">You can create Component Object Model (COM) wrappers by using [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="94741-104">Оба метода позволяют создать два типа программ-оболочек COM:</span><span class="sxs-lookup"><span data-stu-id="94741-104">Both methods generate two types of COM wrappers:</span></span>  
  
-   <span data-ttu-id="94741-105">[Вызываемая оболочка времени выполнения](../../../docs/framework/interop/runtime-callable-wrapper.md) из библиотеки типов для выполнения COM-объектов в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="94741-105">A [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>  
  
-   <span data-ttu-id="94741-106">[Вызываемая оболочка COM](../../../docs/framework/interop/com-callable-wrapper.md) с соответствующими параметрами реестра для выполнения управляемого объекта в собственном приложении.</span><span class="sxs-lookup"><span data-stu-id="94741-106">A [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>  
  
 <span data-ttu-id="94741-107">В [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] оболочку COM можно добавить в проект в виде ссылки.</span><span class="sxs-lookup"><span data-stu-id="94741-107">In [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], you can add the COM wrapper as a reference to your project.</span></span>  
  
## <a name="wrapping-com-objects-in-a-managed-application"></a><span data-ttu-id="94741-108">Создание оболочек для COM-объектов в управляемом приложении</span><span class="sxs-lookup"><span data-stu-id="94741-108">Wrapping COM Objects in a Managed Application</span></span>  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="94741-109">Создание вызываемой оболочки времени выполнения с использованием Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94741-109">To create a runtime callable wrapper using Visual Studio</span></span>  
  
1.  <span data-ttu-id="94741-110">Откройте проект управляемого приложения.</span><span class="sxs-lookup"><span data-stu-id="94741-110">Open the project for your managed application.</span></span>  
  
2.  <span data-ttu-id="94741-111">В меню **Проект** выберите пункт **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="94741-111">On the **Project** menu, click **Show All Files**.</span></span>  
  
3.  <span data-ttu-id="94741-112">В меню **Проект** щелкните команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="94741-112">On the **Project** menu, click **Add Reference**.</span></span>  
  
4.  <span data-ttu-id="94741-113">В диалоговом окне "Добавление ссылки" перейдите на вкладку **COM**, выберите нужный компонент и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="94741-113">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>  
  
     <span data-ttu-id="94741-114">Обратите внимание, что в **обозревателе решений** в папку ссылок проекта добавляется COM-компонент.</span><span class="sxs-lookup"><span data-stu-id="94741-114">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>  
  
 <span data-ttu-id="94741-115">Теперь можно написать код для доступа к COM-объекту.</span><span class="sxs-lookup"><span data-stu-id="94741-115">You can now write code to access the COM object.</span></span> <span data-ttu-id="94741-116">Сначала можно объявить объект, например с помощью оператора `Imports` для [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] или `Using` для [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94741-116">You can begin by declaring the object, such as with an `Imports` statement for [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] or a `Using` statement for [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94741-117">При программировании компонентов Microsoft Office сначала необходимо установить [основные сборки взаимодействия Microsoft Office](http://go.microsoft.com/fwlink/?LinkId=50479) из Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="94741-117">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies](http://go.microsoft.com/fwlink/?LinkId=50479) (PIAs) from the Microsoft Download Center.</span></span> <span data-ttu-id="94741-118">На шаге 4 выберите последнюю доступную версию библиотеки объектов для нужного продукта Office, например **библиотеку объектов Microsoft Word 11.0**.</span><span class="sxs-lookup"><span data-stu-id="94741-118">In step 4, select the latest version of the object library available for the Office product you want, such as the **Microsoft Word 11.0 Object Library**.</span></span>  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="94741-119">Создание вызываемой оболочки времени выполнения с использованием средств платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="94741-119">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
-   <span data-ttu-id="94741-120">Запустите средство [Tlbimp.exe (программа экспорта библиотек типов)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="94741-120">Run the [Tlbimp.exe (Type Library Importer)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="94741-121">Это средство создает сборку, которая содержит метаданные времени выполнения для типов, определенных в исходной библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="94741-121">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrapping-managed-objects-in-a-native-application"></a><span data-ttu-id="94741-122">Создание оболочек для управляемых объектов в собственном приложении</span><span class="sxs-lookup"><span data-stu-id="94741-122">Wrapping Managed Objects in a Native Application</span></span>  
  
#### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="94741-123">Создание вызываемой оболочки COM с использованием Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94741-123">To create a COM callable wrapper using Visual Studio</span></span>  
  
1.  <span data-ttu-id="94741-124">Создайте проект библиотеки классов для управляемого класса, который требуется выполнять в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="94741-124">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="94741-125">Этот класс должен иметь конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="94741-125">The class must have a default constructor.</span></span>  
  
     <span data-ttu-id="94741-126">Убедитесь, что в файле AssemblyInfo присутствует полный номер версии сборки, состоящий из четырех частей.</span><span class="sxs-lookup"><span data-stu-id="94741-126">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="94741-127">Этот номер необходим для управления версиями в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="94741-127">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="94741-128">Дополнительные сведения о номерах версий см. в разделе [Управление версиями сборки](../../../docs/framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="94741-128">For more information about version numbers, see [Assembly Versioning](../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
2.  <span data-ttu-id="94741-129">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="94741-129">On the **Project** menu, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="94741-130">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="94741-130">Click the **Compile** tab.</span></span>  
  
4.  <span data-ttu-id="94741-131">Установите флажок **Регистрация для COM-взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="94741-131">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="94741-132">При построении проекта сборка автоматически регистрируется для COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="94741-132">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="94741-133">При создании собственного приложения в [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] можно использовать сборку, щелкнув команду **Добавить ссылку** в меню **Проект**.</span><span class="sxs-lookup"><span data-stu-id="94741-133">If you are building a native application in [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
#### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="94741-134">Создание вызываемой оболочки COM с использованием средств платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="94741-134">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
-   <span data-ttu-id="94741-135">Запустите программу [Regasm.exe (средство регистрации сборок)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md).</span><span class="sxs-lookup"><span data-stu-id="94741-135">Run the [Regasm.exe (Assembly Registration Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
 <span data-ttu-id="94741-136">Это средство считывает метаданные сборки и добавляет в реестр необходимые записи.</span><span class="sxs-lookup"><span data-stu-id="94741-136">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="94741-137">В результате этого клиенты COM получают возможность прозрачно создавать классы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="94741-137">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="94741-138">Сборку можно использовать так, как если бы она была собственным COM-классом.</span><span class="sxs-lookup"><span data-stu-id="94741-138">You can use the assembly as if it were a native COM class.</span></span>  
  
 <span data-ttu-id="94741-139">Программу Regasm.exe можно запускать для сборки, расположенной в любом каталоге. После этого необходимо запустить [Gacutil.exe (программу глобального кэша сборок)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), чтобы перенести ее в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="94741-139">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="94741-140">При переносе сборки записи расположения в реестре сохраняют силу, поскольку во всех случаях, когда сборка не найдена, проверяется глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="94741-140">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94741-141">См. также</span><span class="sxs-lookup"><span data-stu-id="94741-141">See Also</span></span>  
 [<span data-ttu-id="94741-142">Вызываемая оболочка времени выполнения</span><span class="sxs-lookup"><span data-stu-id="94741-142">Runtime Callable Wrapper</span></span>](../../../docs/framework/interop/runtime-callable-wrapper.md)  
 [<span data-ttu-id="94741-143">Вызываемая оболочка COM</span><span class="sxs-lookup"><span data-stu-id="94741-143">COM Callable Wrapper</span></span>](../../../docs/framework/interop/com-callable-wrapper.md)
