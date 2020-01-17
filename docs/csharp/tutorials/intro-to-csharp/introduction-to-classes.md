---
title: Классы и объекты. Вводное руководство по C#.
description: Создайте свою первую программу на C# и ознакомьтесь с основными понятиями объектно-ориентированного программирования
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 06d1a30abc0d031badcba4ec60f7deb3c670a3ae
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634954"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="f13ea-103">Сведения об использовании классов и объектов в объектно-ориентированном программировании</span><span class="sxs-lookup"><span data-stu-id="f13ea-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="f13ea-104">Для работы с этим руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="f13ea-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="f13ea-105">В руководстве .NET по созданию программы [Hello World за 10 минут](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) содержатся инструкции по настройке локальной среды разработки в macOS, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="f13ea-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="f13ea-106">Краткий обзор команд, которые будут здесь использоваться, и ссылки на дополнительные сведения представлены в статье, посвященной [средствам разработки для .NET](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f13ea-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="f13ea-107">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="f13ea-107">Create your application</span></span>

<span data-ttu-id="f13ea-108">С помощью окна терминала создайте каталог с именем *classes*.</span><span class="sxs-lookup"><span data-stu-id="f13ea-108">Using a terminal window, create a directory named *classes*.</span></span> <span data-ttu-id="f13ea-109">В этом каталоге вы создадите приложение.</span><span class="sxs-lookup"><span data-stu-id="f13ea-109">You'll build your application there.</span></span> <span data-ttu-id="f13ea-110">Откройте этот каталог и введите в окне консоли `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="f13ea-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="f13ea-111">При помощи этой команды создается приложение.</span><span class="sxs-lookup"><span data-stu-id="f13ea-111">This command creates your application.</span></span> <span data-ttu-id="f13ea-112">Откройте файл *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="f13ea-112">Open *Program.cs*.</span></span> <span data-ttu-id="f13ea-113">Он должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="f13ea-113">It should look like this:</span></span>

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="f13ea-114">При работе с этим руководством вы создадите новые типы, представляющие банковский счет.</span><span class="sxs-lookup"><span data-stu-id="f13ea-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="f13ea-115">Обычно разработчики определяют каждый класс в отдельном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="f13ea-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="f13ea-116">Благодаря этому программой легче управлять, когда ее размер увеличивается.</span><span class="sxs-lookup"><span data-stu-id="f13ea-116">That makes it easier to manage as a program grows in size.</span></span> <span data-ttu-id="f13ea-117">Создайте новый файл с именем *BankAccount.cs* в каталоге *classes*.</span><span class="sxs-lookup"><span data-stu-id="f13ea-117">Create a new file named *BankAccount.cs* in the *classes* directory.</span></span> 

<span data-ttu-id="f13ea-118">Этот файл будет содержать определение ***банковского счета***.</span><span class="sxs-lookup"><span data-stu-id="f13ea-118">This file will contain the definition of a ***bank account***.</span></span> <span data-ttu-id="f13ea-119">Средства объектно-ориентированного программирования обеспечивают упорядочение кода. При этом создаются типы в виде ***классов***.</span><span class="sxs-lookup"><span data-stu-id="f13ea-119">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="f13ea-120">Классы содержат код, который представляет отдельную сущность.</span><span class="sxs-lookup"><span data-stu-id="f13ea-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="f13ea-121">Класс `BankAccount` представляет банковский счет.</span><span class="sxs-lookup"><span data-stu-id="f13ea-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="f13ea-122">Этот код реализует определенные операции с помощью методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="f13ea-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="f13ea-123">Созданный в этом кратком руководстве банковский счет поддерживает следующий алгоритм работы:</span><span class="sxs-lookup"><span data-stu-id="f13ea-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="f13ea-124">Представляет собой число из 10 цифр, которое однозначно определяет банковский счет.</span><span class="sxs-lookup"><span data-stu-id="f13ea-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="f13ea-125">Содержит строку, в которой хранятся имена владельцев.</span><span class="sxs-lookup"><span data-stu-id="f13ea-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="f13ea-126">Позволяет получить данные сальдо.</span><span class="sxs-lookup"><span data-stu-id="f13ea-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="f13ea-127">Принимает депозиты.</span><span class="sxs-lookup"><span data-stu-id="f13ea-127">It accepts deposits.</span></span>
1. <span data-ttu-id="f13ea-128">Принимает списания.</span><span class="sxs-lookup"><span data-stu-id="f13ea-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="f13ea-129">Начальное сальдо должно было положительным.</span><span class="sxs-lookup"><span data-stu-id="f13ea-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="f13ea-130">После списания не должно оставаться отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="f13ea-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="f13ea-131">Определение типа банковского счета</span><span class="sxs-lookup"><span data-stu-id="f13ea-131">Define the bank account type</span></span>

<span data-ttu-id="f13ea-132">Сначала можно создать основы класса, который определяет такой режим работы.</span><span class="sxs-lookup"><span data-stu-id="f13ea-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="f13ea-133">Он должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="f13ea-133">It would look like this:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string note)
        {
        }
    }
}
```

<span data-ttu-id="f13ea-134">Прежде чем продолжить, рассмотрим созданный код.</span><span class="sxs-lookup"><span data-stu-id="f13ea-134">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="f13ea-135">Объявление `namespace` предоставляет способ логического упорядочения кода.</span><span class="sxs-lookup"><span data-stu-id="f13ea-135">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="f13ea-136">Это относительно небольшое руководство, поэтому весь код размещается в одном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="f13ea-136">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="f13ea-137">`public class BankAccount` определяет класс или тип, который вы создаете.</span><span class="sxs-lookup"><span data-stu-id="f13ea-137">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="f13ea-138">Весь код в скобках `{` и `}`, который следует за объявлением класса, определяет состояние и поведение класса.</span><span class="sxs-lookup"><span data-stu-id="f13ea-138">Everything inside the `{` and `}` that follows the class declaration defines the state and behavior of the class.</span></span> <span data-ttu-id="f13ea-139">Есть пять ***элементов*** класса `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="f13ea-139">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="f13ea-140">Первые три элемента представляют собой ***свойства***.</span><span class="sxs-lookup"><span data-stu-id="f13ea-140">The first three are ***properties***.</span></span> <span data-ttu-id="f13ea-141">Свойства являются элементами данных и могут содержать код для запуска проверки или других правил.</span><span class="sxs-lookup"><span data-stu-id="f13ea-141">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="f13ea-142">Последние два элемента являются ***методами***.</span><span class="sxs-lookup"><span data-stu-id="f13ea-142">The last two are ***methods***.</span></span> <span data-ttu-id="f13ea-143">Методы представляют собой блоки кода, которые выполняют только одну функцию.</span><span class="sxs-lookup"><span data-stu-id="f13ea-143">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="f13ea-144">Имя каждого элемента должно содержать достаточно информации, чтобы разработчик мог понять, какие функции выполняет класс.</span><span class="sxs-lookup"><span data-stu-id="f13ea-144">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="f13ea-145">Открытие нового счета</span><span class="sxs-lookup"><span data-stu-id="f13ea-145">Open a new account</span></span>

<span data-ttu-id="f13ea-146">Сначала нужно открыть банковский счет.</span><span class="sxs-lookup"><span data-stu-id="f13ea-146">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="f13ea-147">Когда клиент открывает счет, он должен указать начальное сальдо и сведения о владельцах этого счета.</span><span class="sxs-lookup"><span data-stu-id="f13ea-147">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="f13ea-148">Создайте новый объект типа `BankAccount`, чтобы определить ***конструктор***, который назначает эти значения.</span><span class="sxs-lookup"><span data-stu-id="f13ea-148">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="f13ea-149">***Конструктор*** — это элемент, имя которого совпадает с классом.</span><span class="sxs-lookup"><span data-stu-id="f13ea-149">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="f13ea-150">Он используется для инициализации объектов этого типа класса.</span><span class="sxs-lookup"><span data-stu-id="f13ea-150">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="f13ea-151">Добавьте следующий конструктор в тип `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="f13ea-151">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="f13ea-152">Конструкторы вызываются при создании объекта с помощью [`new`](../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f13ea-152">Constructors are called when you create an object using [`new`](../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="f13ea-153">Замените строку `Console.WriteLine("Hello World!");` в файле *Program.cs* следующим кодом (замените `<name>` своим именем):</span><span class="sxs-lookup"><span data-stu-id="f13ea-153">Replace the line `Console.WriteLine("Hello World!");` in *Program.cs* with the following code (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="f13ea-154">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="f13ea-154">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="f13ea-155">Вы заметили, что номер счета не указан?</span><span class="sxs-lookup"><span data-stu-id="f13ea-155">Did you notice that the account number is blank?</span></span> <span data-ttu-id="f13ea-156">Нужно решить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="f13ea-156">It's time to fix that.</span></span> <span data-ttu-id="f13ea-157">Номер счета следует назначить при создании объекта.</span><span class="sxs-lookup"><span data-stu-id="f13ea-157">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="f13ea-158">Но создавать этот номер не входит в обязанности вызывающего.</span><span class="sxs-lookup"><span data-stu-id="f13ea-158">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="f13ea-159">Код класса `BankAccount` должен иметь информацию о том, как присвоить номера новым счетам.</span><span class="sxs-lookup"><span data-stu-id="f13ea-159">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="f13ea-160">Проще всего начать с 10-значного числа.</span><span class="sxs-lookup"><span data-stu-id="f13ea-160">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="f13ea-161">Увеличивайте его при создании каждого нового счета.</span><span class="sxs-lookup"><span data-stu-id="f13ea-161">Increment it when each new account is created.</span></span> <span data-ttu-id="f13ea-162">Затем при создании объекта сохраните номер текущего счета.</span><span class="sxs-lookup"><span data-stu-id="f13ea-162">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="f13ea-163">Добавьте в класс `BankAccount` следующее объявление элемента:</span><span class="sxs-lookup"><span data-stu-id="f13ea-163">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="f13ea-164">Это элемент данных.</span><span class="sxs-lookup"><span data-stu-id="f13ea-164">This is a data member.</span></span> <span data-ttu-id="f13ea-165">Он имеет свойство `private`, то есть к нему может получить доступ только код внутри класса `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="f13ea-165">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="f13ea-166">Таким образом общедоступные обязательства (например, получение номера счета) отделяются от закрытой реализации (способ создания номеров счетов).</span><span class="sxs-lookup"><span data-stu-id="f13ea-166">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated).</span></span> <span data-ttu-id="f13ea-167">Также он является `static`, то есть совместно используется всеми объектами `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="f13ea-167">It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="f13ea-168">Значение нестатической переменной является уникальным для каждого экземпляра объекта `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="f13ea-168">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="f13ea-169">Добавьте две следующие строки в конструктор, чтобы назначить номер счета:</span><span class="sxs-lookup"><span data-stu-id="f13ea-169">Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="f13ea-170">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="f13ea-170">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="f13ea-171">Создание депозитов и списаний</span><span class="sxs-lookup"><span data-stu-id="f13ea-171">Create deposits and withdrawals</span></span>

<span data-ttu-id="f13ea-172">Для надлежащей работы ваш класс банковского счета должен принимать депозиты и списания.</span><span class="sxs-lookup"><span data-stu-id="f13ea-172">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="f13ea-173">Чтобы реализовать депозиты и списания, создадим журнал для каждой транзакции на счете.</span><span class="sxs-lookup"><span data-stu-id="f13ea-173">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="f13ea-174">Этот подход предпочтительнее, чем простое обновление сальдо после каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="f13ea-174">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="f13ea-175">Журнал можно использовать для аудита всех транзакций и управления ежедневным сальдо.</span><span class="sxs-lookup"><span data-stu-id="f13ea-175">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="f13ea-176">При необходимости можно вычислять сальдо с помощью журнала всех транзакций. Тогда при следующем вычислении все исправленные ошибки в одной транзакции будут правильно учтены в сальдо.</span><span class="sxs-lookup"><span data-stu-id="f13ea-176">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="f13ea-177">Начнем с создания нового типа, который представляет транзакцию.</span><span class="sxs-lookup"><span data-stu-id="f13ea-177">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="f13ea-178">Это простой тип без обязательств.</span><span class="sxs-lookup"><span data-stu-id="f13ea-178">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="f13ea-179">Ему нужно назначить несколько свойств.</span><span class="sxs-lookup"><span data-stu-id="f13ea-179">It needs a few properties.</span></span> <span data-ttu-id="f13ea-180">Создайте новый файл с именем *Transaction.cs*.</span><span class="sxs-lookup"><span data-stu-id="f13ea-180">Create a new file named *Transaction.cs*.</span></span> <span data-ttu-id="f13ea-181">Добавьте в этот файл следующий код:</span><span class="sxs-lookup"><span data-stu-id="f13ea-181">Add the following code to it:</span></span>

[!code-csharp[Transaction](~/samples/csharp/classes-quickstart/Transaction.cs)]

<span data-ttu-id="f13ea-182">Теперь добавим <xref:System.Collections.Generic.List%601> объектов `Transaction` в класс `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="f13ea-182">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="f13ea-183">Добавьте следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="f13ea-183">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](~/samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration)]

<span data-ttu-id="f13ea-184">Класс <xref:System.Collections.Generic.List%601> требует импортировать другое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="f13ea-184">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="f13ea-185">Добавьте следующий код в начало файла *BankAccount.cs*:</span><span class="sxs-lookup"><span data-stu-id="f13ea-185">Add the following at the beginning of *BankAccount.cs*:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="f13ea-186">Теперь изменим способ отчета `Balance`.</span><span class="sxs-lookup"><span data-stu-id="f13ea-186">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="f13ea-187">Чтобы вычислить его, нужно суммировать значения всех транзакций.</span><span class="sxs-lookup"><span data-stu-id="f13ea-187">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="f13ea-188">Измените объявление `Balance` в классе `BankAccount` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f13ea-188">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](~/samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation)]

<span data-ttu-id="f13ea-189">В этом примере показан важный аспект ***свойств***.</span><span class="sxs-lookup"><span data-stu-id="f13ea-189">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="f13ea-190">Вы вычисляете сальдо, когда другой программист запрашивает значение.</span><span class="sxs-lookup"><span data-stu-id="f13ea-190">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="f13ea-191">В результате вашего вычисления выводится список всех транзакций и сумма в виде текущего сальдо.</span><span class="sxs-lookup"><span data-stu-id="f13ea-191">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="f13ea-192">Теперь реализуйте методы `MakeDeposit` и `MakeWithdrawal`.</span><span class="sxs-lookup"><span data-stu-id="f13ea-192">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="f13ea-193">Эти методы будут выполнять два последних правила: начальное сальдо должно быть положительным, списание не должно создавать отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="f13ea-193">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="f13ea-194">Это действие вводит понятие ***исключений***.</span><span class="sxs-lookup"><span data-stu-id="f13ea-194">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="f13ea-195">Чтобы определить, что метод не может выполнить свою функцию, обычно вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="f13ea-195">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="f13ea-196">В типе исключения и связанном с ним сообщении описывается ошибка.</span><span class="sxs-lookup"><span data-stu-id="f13ea-196">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="f13ea-197">В этом примере метод `MakeDeposit` вызывает исключение, если сумма депозита является отрицательной.</span><span class="sxs-lookup"><span data-stu-id="f13ea-197">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="f13ea-198">Метод `MakeWithdrawal` вызывает исключение, если сумма списания является отрицательной или если при применении списания создается отрицательное сальдо:</span><span class="sxs-lookup"><span data-stu-id="f13ea-198">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](~/samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal)]

<span data-ttu-id="f13ea-199">Инструкция [`throw`](../../language-reference/keywords/throw.md)**вызывает** исключение.</span><span class="sxs-lookup"><span data-stu-id="f13ea-199">The [`throw`](../../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="f13ea-200">Выполнение текущего блока завершается и управление передается в первый подходящий блок `catch` из стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="f13ea-200">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="f13ea-201">Вы добавите блок `catch` для тестирования этого кода немного позже.</span><span class="sxs-lookup"><span data-stu-id="f13ea-201">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="f13ea-202">Чтобы вместо непосредственного обновления сальдо добавлялась начальная транзакция, конструктор должен получить одно изменение.</span><span class="sxs-lookup"><span data-stu-id="f13ea-202">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="f13ea-203">Так как вы уже написали метод `MakeDeposit`, вызовите его из конструктора.</span><span class="sxs-lookup"><span data-stu-id="f13ea-203">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="f13ea-204">Готовый конструктор должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="f13ea-204">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](~/samples/csharp/classes-quickstart/BankAccount.cs#Constructor)]

<span data-ttu-id="f13ea-205"><xref:System.DateTime.Now?displayProperty=nameWithType> — это свойство, которое возвращает текущие дату и время.</span><span class="sxs-lookup"><span data-stu-id="f13ea-205"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="f13ea-206">Протестируйте его, добавив несколько депозитов и списаний в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="f13ea-206">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="f13ea-207">Теперь протестируйте обнаружение условий ошибки. Для этого создайте счет с отрицательным сальдо:</span><span class="sxs-lookup"><span data-stu-id="f13ea-207">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive.
try
{
    var invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="f13ea-208">С помощью [инструкций `try` и `catch`](../../language-reference/keywords/try-catch.md) пометьте блок кода, который может вызывать исключения, и перехватывайте ожидаемые сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="f13ea-208">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="f13ea-209">Этим же способом можно проверять код, который вызывает исключение при получении отрицательного баланса:</span><span class="sxs-lookup"><span data-stu-id="f13ea-209">You can use the same technique to test the code that throws an exception for a negative balance:</span></span>

```csharp
// Test for a negative balance.
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="f13ea-210">Сохраните файл и введите `dotnet run` для проверки.</span><span class="sxs-lookup"><span data-stu-id="f13ea-210">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="f13ea-211">Задача — регистрация всех транзакций</span><span class="sxs-lookup"><span data-stu-id="f13ea-211">Challenge - log all transactions</span></span>

<span data-ttu-id="f13ea-212">В завершение вы создадите метод `GetAccountHistory`, который создает `string` для журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="f13ea-212">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="f13ea-213">Добавьте этот метод в тип `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="f13ea-213">Add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](~/samples/csharp/classes-quickstart/BankAccount.cs#History)]

<span data-ttu-id="f13ea-214">В этом примере используется класс <xref:System.Text.StringBuilder>, чтобы отформатировать строку, которая содержит одну строку для каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="f13ea-214">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="f13ea-215">Код форматирования строки вы уже видели в этой серии руководств.</span><span class="sxs-lookup"><span data-stu-id="f13ea-215">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="f13ea-216">В этом коде есть новый символ `\t`.</span><span class="sxs-lookup"><span data-stu-id="f13ea-216">One new character is `\t`.</span></span> <span data-ttu-id="f13ea-217">Он позволяет вставить вкладку для форматирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f13ea-217">That inserts a tab to format the output.</span></span>

<span data-ttu-id="f13ea-218">Добавьте следующую строку, чтобы проверить его в файле *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="f13ea-218">Add this line to test it in *Program.cs*:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="f13ea-219">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="f13ea-219">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f13ea-220">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f13ea-220">Next steps</span></span>

<span data-ttu-id="f13ea-221">Если у вас возникли проблемы, изучите исходный код для этого руководства, размещенный [в репозитории GitHub](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/).</span><span class="sxs-lookup"><span data-stu-id="f13ea-221">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/).</span></span>

<span data-ttu-id="f13ea-222">Поздравляем, вы завершили работу с циклом вводных руководств по C#.</span><span class="sxs-lookup"><span data-stu-id="f13ea-222">Congratulations, you've finished all our introduction to C# tutorials.</span></span> <span data-ttu-id="f13ea-223">Если вы хотите узнать больше, обратитесь к другим [руководствам](../index.md).</span><span class="sxs-lookup"><span data-stu-id="f13ea-223">If you're eager to learn more, try more of our [tutorials](../index.md).</span></span>
