---
title: Руководство по началу работы с классами. Краткие руководства по локальной разработке на C#
description: Создайте свою первую программу на C# и ознакомьтесь с основными понятиями объектно-ориентированного программирования
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: a951c84396e187b5ef1a832705b7722f818c990b
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457337"
---
# <a name="introduction-to-classes"></a><span data-ttu-id="52356-103">Общие сведения о классах</span><span class="sxs-lookup"><span data-stu-id="52356-103">Introduction to classes</span></span>

<span data-ttu-id="52356-104">Для работы с этим кратким руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="52356-104">This quickstart expects that you have a machine you can use for development.</span></span> <span data-ttu-id="52356-105">В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="52356-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="52356-106">Краткий обзор команд, которые будут здесь использоваться, и ссылки на дополнительные сведения представлены в [вводной статье к руководствам по локальной разработке](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="52356-106">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="52356-107">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="52356-107">Create your application</span></span>

<span data-ttu-id="52356-108">С помощью окна терминала создайте каталог с именем **classes**.</span><span class="sxs-lookup"><span data-stu-id="52356-108">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="52356-109">В этом каталоге вы создадите приложение.</span><span class="sxs-lookup"><span data-stu-id="52356-109">You'll build your application there.</span></span> <span data-ttu-id="52356-110">Откройте этот каталог и введите в окне консоли `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="52356-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="52356-111">При помощи этой команды создается приложение.</span><span class="sxs-lookup"><span data-stu-id="52356-111">This command creates your application.</span></span> <span data-ttu-id="52356-112">Откройте файл **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="52356-112">Open **Program.cs**.</span></span> <span data-ttu-id="52356-113">Он должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="52356-113">It should look like this:</span></span>

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

<span data-ttu-id="52356-114">При работе с этим кратким руководством вы создадите новые типы, представляющие банковский счет.</span><span class="sxs-lookup"><span data-stu-id="52356-114">In this quickstart, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="52356-115">Обычно разработчики определяют каждый класс в отдельном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="52356-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="52356-116">Благодаря этому программой легче управлять, когда ее размер увеличивается.</span><span class="sxs-lookup"><span data-stu-id="52356-116">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="52356-117">Создайте новый файл с именем **BankAccount.cs** в каталоге **classes**.</span><span class="sxs-lookup"><span data-stu-id="52356-117">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="52356-118">Этот файл будет содержать определение ***банковского счета***.</span><span class="sxs-lookup"><span data-stu-id="52356-118">This file will contain the definition of a ***bank account***.</span></span> <span data-ttu-id="52356-119">Средства объектно-ориентированного программирования обеспечивают упорядочение кода. При этом создаются типы в виде ***классов***.</span><span class="sxs-lookup"><span data-stu-id="52356-119">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="52356-120">Классы содержат код, который представляет отдельную сущность.</span><span class="sxs-lookup"><span data-stu-id="52356-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="52356-121">Класс `BankAccount` представляет банковский счет.</span><span class="sxs-lookup"><span data-stu-id="52356-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="52356-122">Этот код реализует определенные операции с помощью методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="52356-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="52356-123">В этом кратком руководстве банковский счет поддерживает следующий алгоритм работы.</span><span class="sxs-lookup"><span data-stu-id="52356-123">In this quickstart, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="52356-124">Представляет собой число из 10 цифр, которое однозначно определяет банковский счет.</span><span class="sxs-lookup"><span data-stu-id="52356-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="52356-125">Содержит строку, в которой хранятся имена владельцев.</span><span class="sxs-lookup"><span data-stu-id="52356-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="52356-126">Позволяет получить данные сальдо.</span><span class="sxs-lookup"><span data-stu-id="52356-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="52356-127">Принимает депозиты.</span><span class="sxs-lookup"><span data-stu-id="52356-127">It accepts deposits.</span></span>
1. <span data-ttu-id="52356-128">Принимает списания.</span><span class="sxs-lookup"><span data-stu-id="52356-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="52356-129">Начальное сальдо должно было положительным.</span><span class="sxs-lookup"><span data-stu-id="52356-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="52356-130">После списания не должно оставаться отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="52356-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="52356-131">Определение типа банковского счета</span><span class="sxs-lookup"><span data-stu-id="52356-131">Define the bank account type</span></span>

<span data-ttu-id="52356-132">Сначала можно создать основы класса, который определяет такой режим работы.</span><span class="sxs-lookup"><span data-stu-id="52356-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="52356-133">Он должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="52356-133">It would look like this:</span></span>

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

<span data-ttu-id="52356-134">Прежде чем продолжить, рассмотрим созданный код.</span><span class="sxs-lookup"><span data-stu-id="52356-134">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="52356-135">Объявление `namespace` предоставляет способ логического упорядочения кода.</span><span class="sxs-lookup"><span data-stu-id="52356-135">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="52356-136">Это относительно небольшое руководство, поэтому весь код будет находиться в одном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="52356-136">This quickstart is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="52356-137">`public class BankAccount` определяет класс или тип, который вы создаете.</span><span class="sxs-lookup"><span data-stu-id="52356-137">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="52356-138">Весь код в скобках `{` и `}`, который следует за объявлением класса, определяет поведение класса.</span><span class="sxs-lookup"><span data-stu-id="52356-138">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="52356-139">Есть пять ***элементов*** класса `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="52356-139">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="52356-140">Первые три элемента представляют собой ***свойства***.</span><span class="sxs-lookup"><span data-stu-id="52356-140">The first three are ***properties***.</span></span> <span data-ttu-id="52356-141">Свойства являются элементами данных и могут содержать код для запуска проверки или других правил.</span><span class="sxs-lookup"><span data-stu-id="52356-141">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="52356-142">Последние два элемента являются ***методами***.</span><span class="sxs-lookup"><span data-stu-id="52356-142">The last two are ***methods***.</span></span> <span data-ttu-id="52356-143">Методы представляют собой блоки кода, которые выполняют только одну функцию.</span><span class="sxs-lookup"><span data-stu-id="52356-143">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="52356-144">Имя каждого элемента должно содержать достаточно информации, чтобы разработчик мог понять, какие функции выполняет класс.</span><span class="sxs-lookup"><span data-stu-id="52356-144">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="52356-145">Открытие нового счета</span><span class="sxs-lookup"><span data-stu-id="52356-145">Open a new account</span></span>

<span data-ttu-id="52356-146">Сначала нужно открыть банковский счет.</span><span class="sxs-lookup"><span data-stu-id="52356-146">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="52356-147">Когда клиент открывает счет, он должен указать начальное сальдо и сведения о владельцах этого счета.</span><span class="sxs-lookup"><span data-stu-id="52356-147">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="52356-148">Создайте новый объект типа `BankAccount`, чтобы определить ***конструктор***, который назначает эти значения.</span><span class="sxs-lookup"><span data-stu-id="52356-148">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="52356-149">***Конструктор*** — это элемент, имя которого совпадает с классом.</span><span class="sxs-lookup"><span data-stu-id="52356-149">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="52356-150">Он используется для инициализации объектов этого типа класса.</span><span class="sxs-lookup"><span data-stu-id="52356-150">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="52356-151">Добавьте следующий конструктор в тип `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="52356-151">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="52356-152">Конструкторы вызываются при создании объекта с помощью [`new`](../language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="52356-152">Constructors are called when you create an object using [`new`](../language-reference/keywords/new.md).</span></span> <span data-ttu-id="52356-153">Замените строку `Console.WriteLine("Hello World!");` в файле ***program.cs*** следующей строкой (замените `<name>` своим именем):</span><span class="sxs-lookup"><span data-stu-id="52356-153">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="52356-154">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="52356-154">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="52356-155">Вы заметили, что номер счета не указан?</span><span class="sxs-lookup"><span data-stu-id="52356-155">Did you notice that the account number is blank?</span></span> <span data-ttu-id="52356-156">Нужно решить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="52356-156">It's time to fix that.</span></span> <span data-ttu-id="52356-157">Номер счета следует назначить при создании объекта.</span><span class="sxs-lookup"><span data-stu-id="52356-157">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="52356-158">Но создавать этот номер не входит в обязанности вызывающего.</span><span class="sxs-lookup"><span data-stu-id="52356-158">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="52356-159">Код класса `BankAccount` должен иметь информацию о том, как присвоить номера новым счетам.</span><span class="sxs-lookup"><span data-stu-id="52356-159">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="52356-160">Проще всего начать с 10-значного числа.</span><span class="sxs-lookup"><span data-stu-id="52356-160">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="52356-161">Увеличивайте его при создании каждого нового счета.</span><span class="sxs-lookup"><span data-stu-id="52356-161">Increment it when each new account is created.</span></span> <span data-ttu-id="52356-162">Затем при создании объекта сохраните номер текущего счета.</span><span class="sxs-lookup"><span data-stu-id="52356-162">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="52356-163">Добавьте в класс `BankAccount` следующее объявление элемента:</span><span class="sxs-lookup"><span data-stu-id="52356-163">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="52356-164">Это элемент данных.</span><span class="sxs-lookup"><span data-stu-id="52356-164">This is a data member.</span></span> <span data-ttu-id="52356-165">Он имеет свойство `private`, то есть к нему может получить доступ только код внутри класса `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="52356-165">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="52356-166">Таким образом общедоступные обязательства (например, получение номера счета) отделяются от закрытой реализации (способ создания номеров счетов). Добавьте две следующие строки в конструктор, чтобы назначить номер счета:</span><span class="sxs-lookup"><span data-stu-id="52356-166">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="52356-167">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="52356-167">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="52356-168">Создание депозитов и списаний</span><span class="sxs-lookup"><span data-stu-id="52356-168">Create deposits and withdrawals</span></span>

<span data-ttu-id="52356-169">Для надлежащей работы ваш класс банковского счета должен принимать депозиты и списания.</span><span class="sxs-lookup"><span data-stu-id="52356-169">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="52356-170">Чтобы реализовать депозиты и списания, создадим журнал для каждой транзакции на счете.</span><span class="sxs-lookup"><span data-stu-id="52356-170">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="52356-171">Этот подход предпочтительнее, чем простое обновление сальдо после каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="52356-171">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="52356-172">Журнал можно использовать для аудита всех транзакций и управления ежедневным сальдо.</span><span class="sxs-lookup"><span data-stu-id="52356-172">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="52356-173">При необходимости можно вычислять сальдо с помощью журнала всех транзакций. Тогда при следующем вычислении все исправленные ошибки в одной транзакции будут правильно учтены в сальдо.</span><span class="sxs-lookup"><span data-stu-id="52356-173">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="52356-174">Начнем с создания нового типа, который представляет транзакцию.</span><span class="sxs-lookup"><span data-stu-id="52356-174">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="52356-175">Это простой тип без обязательств.</span><span class="sxs-lookup"><span data-stu-id="52356-175">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="52356-176">Ему нужно назначить несколько свойств.</span><span class="sxs-lookup"><span data-stu-id="52356-176">It needs a few properties.</span></span> <span data-ttu-id="52356-177">Создайте новый файл с именем ***Transaction.cs***.</span><span class="sxs-lookup"><span data-stu-id="52356-177">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="52356-178">Добавьте в этот файл следующий код:</span><span class="sxs-lookup"><span data-stu-id="52356-178">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="52356-179">Теперь добавим <xref:System.Collections.Generic.List%601> объектов `Transaction` в класс `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="52356-179">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="52356-180">Добавьте следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="52356-180">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="52356-181">Класс <xref:System.Collections.Generic.List%601> требует импортировать другое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="52356-181">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="52356-182">Добавьте следующий код в начало файла **BankAccount.cs**:</span><span class="sxs-lookup"><span data-stu-id="52356-182">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="52356-183">Теперь изменим способ отчета `Balance`.</span><span class="sxs-lookup"><span data-stu-id="52356-183">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="52356-184">Чтобы вычислить его, нужно суммировать значения всех транзакций.</span><span class="sxs-lookup"><span data-stu-id="52356-184">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="52356-185">Измените объявление `Balance` в классе `BankAccount` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="52356-185">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="52356-186">В этом примере показан важный аспект ***свойств***.</span><span class="sxs-lookup"><span data-stu-id="52356-186">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="52356-187">Вы вычисляете сальдо, когда другой программист запрашивает значение.</span><span class="sxs-lookup"><span data-stu-id="52356-187">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="52356-188">В результате вашего вычисления выводится список всех транзакций и сумма в виде текущего сальдо.</span><span class="sxs-lookup"><span data-stu-id="52356-188">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="52356-189">Теперь реализуйте методы `MakeDeposit` и `MakeWithdrawal`.</span><span class="sxs-lookup"><span data-stu-id="52356-189">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="52356-190">Эти методы будут выполнять два последних правила: начальное сальдо должно быть положительным, списание не должно создавать отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="52356-190">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="52356-191">Это действие вводит понятие ***исключений***.</span><span class="sxs-lookup"><span data-stu-id="52356-191">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="52356-192">Чтобы определить, что метод не может выполнить свою функцию, обычно вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="52356-192">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="52356-193">В типе исключения и связанном с ним сообщении описывается ошибка.</span><span class="sxs-lookup"><span data-stu-id="52356-193">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="52356-194">В этом примере метод `MakeDeposit` вызывает исключение, если сумма депозита является отрицательной.</span><span class="sxs-lookup"><span data-stu-id="52356-194">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="52356-195">Метод `MakeWithdrawal` вызывает исключение, если сумма списания является отрицательной или если при применении списания создается отрицательное сальдо:</span><span class="sxs-lookup"><span data-stu-id="52356-195">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="52356-196">Инструкция [`throw`](../language-reference/keywords/throw.md) **вызывает** исключение.</span><span class="sxs-lookup"><span data-stu-id="52356-196">The [`throw`](../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="52356-197">Когда будет найден соответствующий блок `catch`, выполнение текущего метода завершится и возобновится.</span><span class="sxs-lookup"><span data-stu-id="52356-197">Execution of the current method ends, and will resume when a matching `catch` block is found.</span></span> <span data-ttu-id="52356-198">Вы добавите блок `catch` для тестирования этого кода немного позже.</span><span class="sxs-lookup"><span data-stu-id="52356-198">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="52356-199">Чтобы вместо непосредственного обновления сальдо добавлялась начальная транзакция, конструктор должен получить одно изменение.</span><span class="sxs-lookup"><span data-stu-id="52356-199">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="52356-200">Так как вы уже написали метод `MakeDeposit`, вызовите его из конструктора.</span><span class="sxs-lookup"><span data-stu-id="52356-200">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="52356-201">Готовый конструктор должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="52356-201">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="52356-202"><xref:System.DateTime.Now?displayProperty=nameWithType> — это свойство, которое возвращает текущие дату и время.</span><span class="sxs-lookup"><span data-stu-id="52356-202"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="52356-203">Протестируйте его, добавив несколько депозитов и списаний в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="52356-203">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="52356-204">Теперь протестируйте обнаружение условий ошибки. Для этого создайте счет с отрицательным сальдо:</span><span class="sxs-lookup"><span data-stu-id="52356-204">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive:
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

<span data-ttu-id="52356-205">С помощью [`try` и `catch` инструкций](../language-reference/keywords/try-catch.md) пометьте блок кода, который может вызывать исключения и обнаруживать потенциальные ошибки.</span><span class="sxs-lookup"><span data-stu-id="52356-205">You use the [`try` and `catch` statements](../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions, and to catch those errors that you expect.</span></span> <span data-ttu-id="52356-206">Таким же образом можно протестировать код, который вызывает исключение в случае создания отрицательного сальдо:</span><span class="sxs-lookup"><span data-stu-id="52356-206">You can use the same technique to test the code that throws for a negative balance:</span></span>

```csharp
// Test for a negative balance
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

<span data-ttu-id="52356-207">Сохраните файл и введите `dotnet run` для проверки.</span><span class="sxs-lookup"><span data-stu-id="52356-207">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="52356-208">Задача — регистрация всех транзакций</span><span class="sxs-lookup"><span data-stu-id="52356-208">Challenge - log all transactions</span></span>

<span data-ttu-id="52356-209">Чтобы завершить работу с этим кратким руководством, вы можете написать метод `GetAccountHistory`, который создает `string` для журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="52356-209">To finish this quickstart, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="52356-210">Добавьте этот метод в тип `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="52356-210">add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="52356-211">В этом примере используется класс <xref:System.Text.StringBuilder>, чтобы отформатировать строку, которая содержит одну строку для каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="52356-211">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="52356-212">Код форматирования строки приведен выше в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="52356-212">You've seen the string formatting code earlier in these quickstarts.</span></span> <span data-ttu-id="52356-213">В этом коде есть новый символ `\t`.</span><span class="sxs-lookup"><span data-stu-id="52356-213">One new character is `\t`.</span></span> <span data-ttu-id="52356-214">Он позволяет вставить вкладку для форматирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="52356-214">That inserts a tab to format the output.</span></span>

<span data-ttu-id="52356-215">Добавьте следующую строку, чтобы проверить его в файле **Program.cs**:</span><span class="sxs-lookup"><span data-stu-id="52356-215">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="52356-216">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="52356-216">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="52356-217">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="52356-217">Next Steps</span></span>

<span data-ttu-id="52356-218">Если у вас возникли проблемы, воспользуйтесь исходным кодом примеров для этого руководства [из репозитория GitHub](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/).</span><span class="sxs-lookup"><span data-stu-id="52356-218">If you got stuck, you can see the source for this quickstart [in our GitHub repo](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="52356-219">Поздравляем! Вы выполнили задачи всех наших кратких руководств.</span><span class="sxs-lookup"><span data-stu-id="52356-219">Congratulations, you've finished all our Quickstarts.</span></span> <span data-ttu-id="52356-220">Если вы хотите узнать больше, обратитесь к нашим [руководствам](../tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="52356-220">If you're eager to learn more, try our [tutorials](../tutorials/index.md)</span></span>
