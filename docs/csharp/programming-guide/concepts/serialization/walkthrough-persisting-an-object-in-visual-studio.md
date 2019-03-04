---
title: Пошаговое руководство. Сохранение объекта с помощью C#
ms.date: 04/26/2018
ms.openlocfilehash: 85b58e93d667d39800538bb2c29d4ba69146e7f3
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975827"
---
# <a name="walkthrough-persisting-an-object-using-c"></a><span data-ttu-id="bfa4f-102">Пошаговое руководство. Сохранение объекта с помощью C\#</span><span class="sxs-lookup"><span data-stu-id="bfa4f-102">Walkthrough: persisting an object using C\#</span></span>

<span data-ttu-id="bfa4f-103">С помощью сериализации можно сохранить данные объекта между экземплярами, что позволит сохранять значения и извлекать их при следующем создании экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-103">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>

<span data-ttu-id="bfa4f-104">В этом пошаговом руководстве будет создан базовый объект `Loan`, а его данные сохранены в файл.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-104">In this walkthrough, you will create a basic `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="bfa4f-105">Затем при повторном создании объекта вы получите данные из файла.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-105">You will then retrieve the data from the file when you re-create the object.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfa4f-106">В этом примере создается файл (если файл отсутствует).</span><span class="sxs-lookup"><span data-stu-id="bfa4f-106">This example creates a new file if the file does not already exist.</span></span> <span data-ttu-id="bfa4f-107">Если приложение должно создать файл, ему необходимо разрешение `Create` для папки.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-107">If an application must create a file, that application must have `Create` permission for the folder.</span></span> <span data-ttu-id="bfa4f-108">Для задания разрешений используются списки управления доступом.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-108">Permissions are set by using access control lists.</span></span> <span data-ttu-id="bfa4f-109">Если файл уже существует, приложению требуется лишь разрешение `Write` (с более низким уровнем).</span><span class="sxs-lookup"><span data-stu-id="bfa4f-109">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="bfa4f-110">Если возможно, безопаснее создать файл во время развертывания и предоставить только разрешения `Read` для одного файла (вместо разрешения Create для папки).</span><span class="sxs-lookup"><span data-stu-id="bfa4f-110">Where possible, it's more secure to create the file during deployment and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="bfa4f-111">По тем же соображениям рекомендуется записывать данные в пользовательские папки, а не в корневую папку или папку Program Files.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-111">Also, it's more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfa4f-112">В этом примере данные сохраняются в двоичном формате.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-112">This example stores data in a binary format file.</span></span> <span data-ttu-id="bfa4f-113">Эти форматы не следует использовать для конфиденциальных данных, таких как пароли или сведения о кредитных картах.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-113">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bfa4f-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="bfa4f-114">Prerequisites</span></span>

* <span data-ttu-id="bfa4f-115">Для сборки и запуска установите [пакет SDK для .NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="bfa4f-115">To build and run, install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="bfa4f-116">Установите любой привычный для вас редактор кода, если еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="bfa4f-117">Нужно ли устанавливать редактор кода?</span><span class="sxs-lookup"><span data-stu-id="bfa4f-117">Need to install a code editor?</span></span> <span data-ttu-id="bfa4f-118">Попробуйте использовать [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="bfa4f-118">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

* <span data-ttu-id="bfa4f-119">Этот пример требует C# версии 7.3.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-119">The example requires C# 7.3.</span></span> <span data-ttu-id="bfa4f-120">См. [сведения о выборе версии языка C#](../../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="bfa4f-120">See [Select the C# language version](../../../language-reference/configure-language-version.md)</span></span> 

<span data-ttu-id="bfa4f-121">Можно просмотреть образец кода онлайн [в репозитории GitHub с примерами .NET](https://github.com/dotnet/samples/tree/master/csharp/serialization).</span><span class="sxs-lookup"><span data-stu-id="bfa4f-121">You can examine the sample code online [at the .NET samples GitHub repository](https://github.com/dotnet/samples/tree/master/csharp/serialization).</span></span>

## <a name="creating-the-loan-object"></a><span data-ttu-id="bfa4f-122">Создание объекта Loan</span><span class="sxs-lookup"><span data-stu-id="bfa4f-122">Creating the loan object</span></span>

<span data-ttu-id="bfa4f-123">Первым шагом является создание класса `Loan` и консольного приложения, которое использует этот класс:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-123">The first step is to create a `Loan` class and a console application that uses the class:</span></span>

1. <span data-ttu-id="bfa4f-124">Создание нового приложения.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-124">Create a new application.</span></span> <span data-ttu-id="bfa4f-125">Введите `dotnet new console -o serialization` для создания нового консольного приложения в подкаталоге `serialization`.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-125">Type `dotnet new console -o serialization` to create a new console application in a subdirectory named `serialization`.</span></span>
1. <span data-ttu-id="bfa4f-126">Откройте приложение в редакторе и добавьте новый класс с именем `Loan.cs`.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-126">Open the application in your editor, and add a new class named `Loan.cs`.</span></span>
1. <span data-ttu-id="bfa4f-127">Добавьте приведенный ниже код к классу `Loan`:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-127">Add the following code to your `Loan` class:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/csharp/serialization/Loan.cs#1)]

<span data-ttu-id="bfa4f-128">Также потребуется создать приложение, которое использует класс `Loan`.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-128">You will also have to create an application that uses the `Loan` class.</span></span>

## <a name="serialize-the-loan-object"></a><span data-ttu-id="bfa4f-129">Сериализация объекта Loan</span><span class="sxs-lookup"><span data-stu-id="bfa4f-129">Serialize the loan object</span></span>

1. <span data-ttu-id="bfa4f-130">Откройте `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-130">Open `Program.cs`.</span></span> <span data-ttu-id="bfa4f-131">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-131">Add the following code:</span></span>

[!code-csharp[Create a loan object](../../../../../samples/csharp/serialization/Program.cs#1)]

<span data-ttu-id="bfa4f-132">Добавьте обработчик событий для события `PropertyChanged` и несколько строк, чтобы изменить объект `Loan` и отобразить изменения.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-132">Add an event handler for the `PropertyChanged` event, and a few lines to modify the `Loan` object and display the changes.</span></span> <span data-ttu-id="bfa4f-133">Дополнения отображаются в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-133">You can see the additions in the following code:</span></span>

[!code-csharp[Listening for the PropertyChanged event](../../../../../samples/csharp/serialization/Program.cs#2)]

<span data-ttu-id="bfa4f-134">На этом этапе можно запустить код и посмотреть текущие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-134">At this point, you can run the code, and see the current output:</span></span>

```console
New customer value: Henry Clay
7.5
7.1
```

<span data-ttu-id="bfa4f-135">При повторном запуске приложения выводятся одни и те же значения.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-135">Running this application repeatedly always writes the same values.</span></span> <span data-ttu-id="bfa4f-136">При каждом запуске программы создается новый объект Loan.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-136">A new Loan object is created every time you run the program.</span></span> <span data-ttu-id="bfa4f-137">В реальной жизни процентная ставка время от времени меняется, но не при каждом запуске этого приложения.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-137">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="bfa4f-138">Код сериализации позволяет сохранять последние процентные ставки между экземплярами приложения.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-138">Serialization code means you preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="bfa4f-139">На следующем шаге для этого в класс Loan будет добавлена сериализация.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-139">In the next step, you will do just that by adding serialization to the Loan class.</span></span>

## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="bfa4f-140">Использование сериализации для хранения объекта</span><span class="sxs-lookup"><span data-stu-id="bfa4f-140">Using Serialization to Persist the Object</span></span>

<span data-ttu-id="bfa4f-141">Чтобы сохранить значения для класса Loan, прежде всего необходимо отметить класс атрибутом `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-141">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span> <span data-ttu-id="bfa4f-142">Добавьте следующий код непосредственно перед определением класса Loan:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-142">Add the following code above the Loan class definition:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/csharp/serialization/Loan.cs#2)]

<span data-ttu-id="bfa4f-143">Атрибут <xref:System.SerializableAttribute> сообщает компилятору, что все находящееся в классе может быть сохранено в файле.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-143">The <xref:System.SerializableAttribute> tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="bfa4f-144">Поскольку событие `PropertyChanged` не представляет часть графа объекта, который должен быть сохранен, оно не подлежит сериализации.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-144">Because the `PropertyChanged` event does not represent part of the object graph that should be stored, it should not be serialized.</span></span> <span data-ttu-id="bfa4f-145">В противном случае будут сериализованы все объекты, присоединенные к этому событию.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-145">Doing so would serialize all objects that are attached to that event.</span></span> <span data-ttu-id="bfa4f-146">Можно добавить <xref:System.NonSerializedAttribute> к объявлению поля для обработчика событий `PropertyChanged`.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-146">You can add the <xref:System.NonSerializedAttribute> to the field declaration for the `PropertyChanged` event handler.</span></span>

[!code-csharp[Disable serialization for the event handler](../../../../../samples/csharp/serialization/Loan.cs#3)]

<span data-ttu-id="bfa4f-147">Начиная с C# 7.3 можно прикреплять атрибуты к резервному полю автоматически реализуемого свойства с помощью значения целевого объекта `field`.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-147">Beginning with C# 7.3, you can attach attributes to the backing field of an auto-implemented property using the `field` target value.</span></span> <span data-ttu-id="bfa4f-148">Следующий код добавляет свойство `TimeLastLoaded` и помечает его как не подлежащее сериализации:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-148">The following code adds a `TimeLastLoaded` property and marks it as not serializable:</span></span>

[!code-csharp[Disable serialization for an auto-implemented property](../../../../../samples/csharp/serialization/Loan.cs#4)]

<span data-ttu-id="bfa4f-149">Следующим шагом будет добавление кода сериализации в приложение LoanApp.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-149">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="bfa4f-150">Чтобы выполнить сериализацию класса и записать данные в файл, используйте пространства имен <xref:System.IO> и <xref:System.Runtime.Serialization.Formatters.Binary>.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-150">In order to serialize the class and write it to a file, you use the <xref:System.IO> and <xref:System.Runtime.Serialization.Formatters.Binary> namespaces.</span></span> <span data-ttu-id="bfa4f-151">Во избежание ввода полных имен можно добавить ссылки на необходимые пространства имен, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-151">To avoid typing the fully qualified names, you can add references to the necessary namespaces as shown in the following code:</span></span>

[!code-csharp[Adding namespaces for serialization](../../../../../samples/csharp/serialization/Program.cs#3)]

<span data-ttu-id="bfa4f-152">Следующим шагом является добавление кода для десериализации объекта из файла при создании объекта.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-152">The next step is to add code to deserialize the object from the file when the object is created.</span></span> <span data-ttu-id="bfa4f-153">Добавьте в класс константу для имени файла сериализованных данных, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-153">Add a constant to the class for the serialized data's file name as shown in the following code:</span></span>

[!code-csharp[Define the name of the saved file](../../../../../samples/csharp/serialization/Program.cs#4)]

<span data-ttu-id="bfa4f-154">Затем добавьте следующий код после строки, которая создает объект `TestLoan`:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-154">Next, add the following code after the line that creates the `TestLoan` object:</span></span>

[!code-csharp[Read from a file if it exists](../../../../../samples/csharp/serialization/Program.cs#5)]

<span data-ttu-id="bfa4f-155">Прежде всего убедитесь, что файл существует.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-155">You first must check that the file exists.</span></span> <span data-ttu-id="bfa4f-156">Если он существует, создайте класс <xref:System.IO.Stream> для чтения двоичного файла и класс <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> для преобразования файла.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-156">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="bfa4f-157">Кроме того, необходимо преобразовать тип потока в тип объекта Loan.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-157">You also need to convert from the stream type to the Loan object type.</span></span>

<span data-ttu-id="bfa4f-158">Далее необходимо добавить код для сериализации класса в файл.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-158">Next you must add code to serialize the class to a file.</span></span> <span data-ttu-id="bfa4f-159">Добавьте следующий код после существующего кода в методе `Main`:</span><span class="sxs-lookup"><span data-stu-id="bfa4f-159">Add the following code after the existing code in the `Main` method:</span></span>

[!code-csharp[Save the existing Loan object](../../../../../samples/csharp/serialization/Program.cs#6)]

<span data-ttu-id="bfa4f-160">Теперь можно снова собрать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-160">At this point, you can again build and run the application.</span></span> <span data-ttu-id="bfa4f-161">При первом запуске вы заметите, что процентная ставка имеет значение 7,5, а затем меняется на 7,1.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-161">The first time it runs, notice that the interest rates starts at 7.5, and then changes to 7.1.</span></span> <span data-ttu-id="bfa4f-162">Закройте приложение, а затем снова запустите его.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-162">Close the application and then run it again.</span></span> <span data-ttu-id="bfa4f-163">Теперь приложение выводит сообщение о том, что сохраненный файл прочитан и процентная ставка составляет 7,1, даже раньше кода, который меняет ее.</span><span class="sxs-lookup"><span data-stu-id="bfa4f-163">Now, the application prints the message that it has read the saved file, and the interest rate is 7.1 even before the code that changes it.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfa4f-164">См. также</span><span class="sxs-lookup"><span data-stu-id="bfa4f-164">See also</span></span>

- [<span data-ttu-id="bfa4f-165">Сериализация (C#)</span><span class="sxs-lookup"><span data-stu-id="bfa4f-165">Serialization (C#)</span></span>](index.md)
- [<span data-ttu-id="bfa4f-166">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bfa4f-166">C# Programming Guide</span></span>](../..//index.md)
