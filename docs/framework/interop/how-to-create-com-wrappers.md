---
title: Практическое руководство. Создание оболочек COM
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
ms.openlocfilehash: 623df8aa86d25d9a57d3039bee01b0ee39d402a8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123941"
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="926d7-102">Практическое руководство. Создание оболочек COM</span><span class="sxs-lookup"><span data-stu-id="926d7-102">How to: Create COM Wrappers</span></span>

<span data-ttu-id="926d7-103">Программы-оболочки модели COM можно создавать с использованием функций Visual Studio 2005 или средств платформы .NET Framework (Tlbimp.exe и Regasm.exe).</span><span class="sxs-lookup"><span data-stu-id="926d7-103">You can create Component Object Model (COM) wrappers by using Visual Studio 2005 features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="926d7-104">Оба метода позволяют создать два типа программ-оболочек COM:</span><span class="sxs-lookup"><span data-stu-id="926d7-104">Both methods generate two types of COM wrappers:</span></span>

- <span data-ttu-id="926d7-105">[Вызываемая оболочка времени выполнения](../../standard/native-interop/runtime-callable-wrapper.md) из библиотеки типов для выполнения COM-объектов в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="926d7-105">A [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>

- <span data-ttu-id="926d7-106">[Вызываемая оболочка COM](../../standard/native-interop/com-callable-wrapper.md) с соответствующими параметрами реестра для выполнения управляемого объекта в собственном приложении.</span><span class="sxs-lookup"><span data-stu-id="926d7-106">A [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>

<span data-ttu-id="926d7-107">В Visual Studio 2005 оболочку COM можно добавить в проект в виде ссылки.</span><span class="sxs-lookup"><span data-stu-id="926d7-107">In Visual Studio 2005, you can add the COM wrapper as a reference to your project.</span></span>

## <a name="wrap-com-objects-in-a-managed-application"></a><span data-ttu-id="926d7-108">Создание оболочек для COM-объектов в управляемом приложении</span><span class="sxs-lookup"><span data-stu-id="926d7-108">Wrap COM Objects in a Managed Application</span></span>

### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="926d7-109">Создание вызываемой оболочки времени выполнения с использованием Visual Studio</span><span class="sxs-lookup"><span data-stu-id="926d7-109">To create a runtime callable wrapper using Visual Studio</span></span>

1. <span data-ttu-id="926d7-110">Откройте проект управляемого приложения.</span><span class="sxs-lookup"><span data-stu-id="926d7-110">Open the project for your managed application.</span></span>

2. <span data-ttu-id="926d7-111">В меню **Проект** выберите пункт **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="926d7-111">On the **Project** menu, click **Show All Files**.</span></span>

3. <span data-ttu-id="926d7-112">В меню **Проект** щелкните команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="926d7-112">On the **Project** menu, click **Add Reference**.</span></span>

4. <span data-ttu-id="926d7-113">В диалоговом окне "Добавление ссылки" перейдите на вкладку **COM**, выберите нужный компонент и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="926d7-113">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>

     <span data-ttu-id="926d7-114">Обратите внимание, что в **обозревателе решений** в папку ссылок проекта добавляется COM-компонент.</span><span class="sxs-lookup"><span data-stu-id="926d7-114">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>

<span data-ttu-id="926d7-115">Теперь можно написать код для доступа к COM-объекту.</span><span class="sxs-lookup"><span data-stu-id="926d7-115">You can now write code to access the COM object.</span></span> <span data-ttu-id="926d7-116">Сначала можно объявить объект, например с помощью оператора `Imports` для Visual Basic или оператора `Using` для C#.</span><span class="sxs-lookup"><span data-stu-id="926d7-116">You can begin by declaring the object, such as with an `Imports` statement for Visual Basic or a `Using` statement for C#.</span></span>

> [!NOTE]
> <span data-ttu-id="926d7-117">При программировании компонентов Microsoft Office сначала необходимо установить [основные сборки взаимодействия Microsoft Office](https://go.microsoft.com/fwlink/?LinkId=50479) из Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="926d7-117">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies](https://go.microsoft.com/fwlink/?LinkId=50479) (PIAs) from the Microsoft Download Center.</span></span> <span data-ttu-id="926d7-118">На шаге 4 выберите последнюю доступную версию библиотеки объектов для нужного продукта Office, например **библиотеку объектов Microsoft Word 11.0**.</span><span class="sxs-lookup"><span data-stu-id="926d7-118">In step 4, select the latest version of the object library available for the Office product you want, such as the **Microsoft Word 11.0 Object Library**.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="926d7-119">Создание вызываемой оболочки времени выполнения с использованием средств платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="926d7-119">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
- <span data-ttu-id="926d7-120">Запустите средство [Tlbimp.exe (программа экспорта библиотек типов)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="926d7-120">Run the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="926d7-121">Это средство создает сборку, которая содержит метаданные времени выполнения для типов, определенных в исходной библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="926d7-121">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrap-managed-objects-in-a-native-application"></a><span data-ttu-id="926d7-122">Создание оболочек для управляемых объектов в собственном приложении</span><span class="sxs-lookup"><span data-stu-id="926d7-122">Wrap Managed Objects in a Native Application</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="926d7-123">Создание вызываемой оболочки COM с использованием Visual Studio</span><span class="sxs-lookup"><span data-stu-id="926d7-123">To create a COM callable wrapper using Visual Studio</span></span>  
  
1. <span data-ttu-id="926d7-124">Создайте проект библиотеки классов для управляемого класса, который требуется выполнять в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="926d7-124">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="926d7-125">Класс должен содержать конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="926d7-125">The class must have a parameterless constructor.</span></span>  
  
     <span data-ttu-id="926d7-126">Убедитесь, что в файле AssemblyInfo присутствует полный номер версии сборки, состоящий из четырех частей.</span><span class="sxs-lookup"><span data-stu-id="926d7-126">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="926d7-127">Этот номер необходим для управления версиями в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="926d7-127">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="926d7-128">Дополнительные сведения о номерах версий см. в разделе [Управление версиями сборки](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="926d7-128">For more information about version numbers, see [Assembly Versioning](../../standard/assembly/versioning.md).</span></span>  
  
2. <span data-ttu-id="926d7-129">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="926d7-129">On the **Project** menu, click **Properties**.</span></span>  
  
3. <span data-ttu-id="926d7-130">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="926d7-130">Click the **Compile** tab.</span></span>  
  
4. <span data-ttu-id="926d7-131">Установите флажок **Регистрация для COM-взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="926d7-131">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="926d7-132">При построении проекта сборка автоматически регистрируется для COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="926d7-132">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="926d7-133">При создании собственного приложения в Visual Studio 2005 можно использовать сборку, щелкнув команду **Добавить ссылку** в меню **Проект**.</span><span class="sxs-lookup"><span data-stu-id="926d7-133">If you are building a native application in Visual Studio 2005, you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="926d7-134">Создание вызываемой оболочки COM с использованием средств платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="926d7-134">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
<span data-ttu-id="926d7-135">Запустите программу [Regasm.exe (средство регистрации сборок)](../tools/regasm-exe-assembly-registration-tool.md).</span><span class="sxs-lookup"><span data-stu-id="926d7-135">Run the [Regasm.exe (Assembly Registration Tool)](../tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
<span data-ttu-id="926d7-136">Это средство считывает метаданные сборки и добавляет в реестр необходимые записи.</span><span class="sxs-lookup"><span data-stu-id="926d7-136">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="926d7-137">В результате этого клиенты COM получают возможность прозрачно создавать классы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="926d7-137">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="926d7-138">Сборку можно использовать так, как если бы она была собственным COM-классом.</span><span class="sxs-lookup"><span data-stu-id="926d7-138">You can use the assembly as if it were a native COM class.</span></span>  
  
<span data-ttu-id="926d7-139">Программу Regasm.exe можно запускать для сборки, расположенной в любом каталоге. После этого необходимо запустить [Gacutil.exe (программу глобального кэша сборок)](../tools/gacutil-exe-gac-tool.md), чтобы перенести ее в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="926d7-139">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="926d7-140">При переносе сборки записи расположения в реестре сохраняют силу, поскольку во всех случаях, когда сборка не найдена, проверяется глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="926d7-140">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="926d7-141">См. также</span><span class="sxs-lookup"><span data-stu-id="926d7-141">See also</span></span>

- [<span data-ttu-id="926d7-142">Вызываемая оболочка времени выполнения</span><span class="sxs-lookup"><span data-stu-id="926d7-142">Runtime Callable Wrapper</span></span>](../../standard/native-interop/runtime-callable-wrapper.md)
- [<span data-ttu-id="926d7-143">Вызываемая оболочка COM</span><span class="sxs-lookup"><span data-stu-id="926d7-143">COM Callable Wrapper</span></span>](../../standard/native-interop/com-callable-wrapper.md)
