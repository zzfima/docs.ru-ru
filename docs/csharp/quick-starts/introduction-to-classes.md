---
title: "Краткие руководства | Общие сведения о классах | Руководство по C#"
description: "Создайте свою первую программу на C# и ознакомьтесь с основными понятиями объектно-ориентированного программирования"
author: billwagner
ms.author: wiwagn
ms.date: 10/11/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 0ddb7508841087571c0cd095b1d1518e4aad50ff
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2017
---
# <a name="introduction-to-classes"></a><span data-ttu-id="a3fc7-103">Общие сведения о классах</span><span class="sxs-lookup"><span data-stu-id="a3fc7-103">Introduction to classes</span></span>

<span data-ttu-id="a3fc7-104">В этом руководстве предполагается, что вы установили [пакет SDK для .NET Core](http://dot.net/core) и любой редактор по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-104">This lesson assumes that you've installed [.NET Core SDK](http://dot.net/core), and an editor of your choice.</span></span> <span data-ttu-id="a3fc7-105">Если у вас нет редактора, попробуйте использовать [Visual Studio Code](https://code.visualstudio.com/) или [Visual Studio](https://www.visualstudio.com/) для Mac или Windows.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-105">If you don't have one, try [Visual Studio Code](https://code.visualstudio.com/), or [Visual Studio](https://www.visualstudio.com/) on Mac or Windows.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="a3fc7-106">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="a3fc7-106">Create your application</span></span>

<span data-ttu-id="a3fc7-107">С помощью окна терминала создайте каталог с именем **classes**.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-107">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="a3fc7-108">В этом каталоге вы создадите приложение.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-108">You'll build your application there.</span></span> <span data-ttu-id="a3fc7-109">Откройте этот каталог и введите в окне консоли `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-109">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="a3fc7-110">При помощи этой команды создается приложение.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-110">This command creates your application.</span></span> <span data-ttu-id="a3fc7-111">Откройте файл **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-111">Open **Program.cs**.</span></span> <span data-ttu-id="a3fc7-112">Он должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-112">It should look like this:</span></span>

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

<span data-ttu-id="a3fc7-113">С помощью этого краткого руководства вы создадите новые типы, представляющие банковский счет.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-113">In this quick start, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="a3fc7-114">Обычно разработчики определяют каждый класс в отдельном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-114">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="a3fc7-115">Благодаря этому программой легче управлять, когда ее размер увеличивается.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-115">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="a3fc7-116">Создайте новый файл с именем **BankAccount.cs** в каталоге **classes**.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-116">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="a3fc7-117">Этот файл будет содержать определение ***банковского счета***.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-117">This file will contain the deefinition of a ***bank account***.</span></span> <span data-ttu-id="a3fc7-118">Средства объектно-ориентированного программирования обеспечивают упорядочение кода. При этом создаются типы в виде ***классов***.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-118">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="a3fc7-119">Классы содержат код, который представляет отдельную сущность.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-119">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="a3fc7-120">Класс `BankAccount` представляет банковский счет.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-120">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="a3fc7-121">Этот код реализует определенные операции с помощью методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-121">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="a3fc7-122">В этом кратком руководстве банковский счет поддерживает следующий режим работы:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-122">In this quick start, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="a3fc7-123">Представляет собой число из 10 цифр, которое однозначно определяет банковский счет.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-123">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="a3fc7-124">Содержит строку, в которой хранятся имена владельцев.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-124">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="a3fc7-125">Позволяет получить данные сальдо.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-125">The balance can be retrieved.</span></span>
1. <span data-ttu-id="a3fc7-126">Принимает депозиты.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-126">It accepts deposits.</span></span>
1. <span data-ttu-id="a3fc7-127">Принимает списания.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-127">It accepts withdrawals.</span></span>
1. <span data-ttu-id="a3fc7-128">Начальное сальдо должно было положительным.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-128">The initial balance must be positive.</span></span>
1. <span data-ttu-id="a3fc7-129">После списания не должно оставаться отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-129">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="a3fc7-130">Определение типа банковского счета</span><span class="sxs-lookup"><span data-stu-id="a3fc7-130">Define the bank account type</span></span>

<span data-ttu-id="a3fc7-131">Сначала можно создать основы класса, который определяет такой режим работы.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-131">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="a3fc7-132">Он должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-132">It would look like this:</span></span>

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

        public void MakeWithdrawal(decimal amount, DateTime date, string payee, string note)
        {
        }
    }
}
```

<span data-ttu-id="a3fc7-133">Прежде чем продолжить, рассмотрим созданный код.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-133">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="a3fc7-134">Объявление `namespace` предоставляет способ логического упорядочения кода.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-134">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="a3fc7-135">Это относительно небольшое руководство, поэтому весь код будет находиться в одном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-135">This quick start is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="a3fc7-136">`public class BankAccount` определяет класс или тип, который вы создаете.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-136">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="a3fc7-137">Весь код в скобках `{` и `}`, который следует за объявлением класса, определяет поведение класса.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-137">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="a3fc7-138">Есть пять ***элементов*** класса `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-138">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="a3fc7-139">Первые три элемента представляют собой ***свойства***.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-139">The first three are ***properties***.</span></span> <span data-ttu-id="a3fc7-140">Свойства являются элементами данных и могут содержать код для запуска проверки или других правил.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-140">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="a3fc7-141">Последние два элемента являются ***методами***.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-141">The last two are ***methods***.</span></span> <span data-ttu-id="a3fc7-142">Методы представляют собой блоки кода, которые выполняют только одну функцию.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-142">Methods are blocks of code that peform a single function.</span></span> <span data-ttu-id="a3fc7-143">Имя каждого элемента должно содержать достаточно информации, чтобы разработчик мог понять, какие функции выполняет класс.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-143">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="a3fc7-144">Открытие нового счета</span><span class="sxs-lookup"><span data-stu-id="a3fc7-144">Open a new account</span></span>

<span data-ttu-id="a3fc7-145">Сначала нужно открыть банковский счет.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-145">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="a3fc7-146">Когда клиент открывает счет, он должен указать начальное сальдо и сведения о владельцах этого счета.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-146">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="a3fc7-147">Создайте новый объект типа `BankAccount`, чтобы определить ***конструктор***, который назначает эти значения.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-147">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="a3fc7-148">***Конструктор*** — это элемент, имя которого совпадает с классом.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-148">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="a3fc7-149">Он используется для инициализации объектов этого типа класса.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-149">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="a3fc7-150">Добавьте следующий конструктор в тип `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-150">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="a3fc7-151">Конструкторы вызываются при создании объекта с помощью [`new`](../language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="a3fc7-151">Constructors are called when you create an object using [`new`](../language-reference/keywords/new.md).</span></span> <span data-ttu-id="a3fc7-152">Замените строку `Console.WriteLine("Hello World!");` в файле ***program.cs*** следующей строкой (замените `<name>` своим именем):</span><span class="sxs-lookup"><span data-stu-id="a3fc7-152">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="a3fc7-153">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-153">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="a3fc7-154">Вы заметили, что номер счета не указан?</span><span class="sxs-lookup"><span data-stu-id="a3fc7-154">Did you notice that the account number is blank?</span></span> <span data-ttu-id="a3fc7-155">Нужно решить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-155">It's time to fix that.</span></span> <span data-ttu-id="a3fc7-156">Номер счета следует назначить при создании объекта.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-156">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="a3fc7-157">Но создавать этот номер не входит в обязанности вызывающего.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-157">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="a3fc7-158">Код класса `BankAccount` должен иметь информацию о том, как присвоить номера новым счетам.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-158">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="a3fc7-159">Проще всего начать с 10-значного числа.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-159">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="a3fc7-160">Увеличивайте его при создании каждого нового счета.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-160">Increment it when each new account is created.</span></span> <span data-ttu-id="a3fc7-161">Затем при создании объекта сохраните номер текущего счета.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-161">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="a3fc7-162">Добавьте в класс `BankAccount` следующее объявление элемента:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-162">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="a3fc7-163">Это элемент данных.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-163">This is a data member.</span></span> <span data-ttu-id="a3fc7-164">Он имеет свойство `private`, то есть к нему может получить доступ только код внутри класса `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-164">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="a3fc7-165">Таким образом общедоступные обязательства (например, получение номера счета) отделяются от закрытой реализации (способ создания номеров счетов). Добавьте две следующие строки в конструктор, чтобы назначить номер счета:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-165">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="a3fc7-166">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-166">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="a3fc7-167">Создание депозитов и списаний</span><span class="sxs-lookup"><span data-stu-id="a3fc7-167">Create deposits and withdrawals</span></span>

<span data-ttu-id="a3fc7-168">Для надлежащей работы ваш класс банковского счета должен принимать депозиты и списания.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-168">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="a3fc7-169">Чтобы реализовать депозиты и списания, создадим журнал для каждой транзакции на счете.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-169">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="a3fc7-170">Этот подход предпочтительнее, чем простое обновление сальдо после каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-170">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="a3fc7-171">Журнал можно использовать для аудита всех транзакций и управления ежедневным сальдо.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-171">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="a3fc7-172">При необходимости можно вычислять сальдо с помощью журнала всех транзакций. Тогда при следующем вычислении все исправленные ошибки в одной транзакции будут правильно учтены в сальдо.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-172">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="a3fc7-173">Начнем с создания нового типа, который представляет транзакцию.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-173">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="a3fc7-174">Это простой тип без обязательств.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-174">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="a3fc7-175">Ему нужно назначить несколько свойств.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-175">It needs a few properties.</span></span> <span data-ttu-id="a3fc7-176">Создайте новый файл с именем ***Transaction.cs***.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-176">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="a3fc7-177">Добавьте в этот файл следующий код:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-177">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="a3fc7-178">Теперь добавим <xref:System.Collections.Generic.List%601> объектов `Transaction` в класс `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-178">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="a3fc7-179">Добавьте следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-179">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="a3fc7-180">Класс <xref:System.Collections.Generic.List%601> требует импортировать другое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-180">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="a3fc7-181">Добавьте следующий код в начало файла **BankAccount.cs**:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-181">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="a3fc7-182">Теперь изменим способ отчета `Balance`.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-182">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="a3fc7-183">Чтобы вычислить его, нужно суммировать значения всех транзакций.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-183">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="a3fc7-184">Измените объявление `Balance` в классе `BankAccount` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-184">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="a3fc7-185">В этом примере показан важный аспект ***свойств***.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-185">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="a3fc7-186">Вы вычисляете сальдо, когда другой программист запрашивает значение.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-186">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="a3fc7-187">В результате вашего вычисления выводится список всех транзакций и сумма в виде текущего сальдо.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-187">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="a3fc7-188">Теперь реализуйте методы `MakeDeposit` и `MakeWithdrawal`.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-188">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="a3fc7-189">Эти методы будут выполнять два последних правила: начальное сальдо должно быть положительным, списание не должно создавать отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-189">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="a3fc7-190">Это действие вводит понятие ***исключений***.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-190">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="a3fc7-191">Чтобы определить, что метод не может выполнить свою функцию, обычно вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-191">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="a3fc7-192">В типе исключения и связанном с ним сообщении описывается ошибка.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-192">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="a3fc7-193">В этом примере метод `MakeDeposit` вызывает исключение, если сумма депозита является отрицательной.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-193">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="a3fc7-194">Метод `MakeWithdrawal` вызывает исключение, если сумма списания является отрицательной или если при применении списания создается отрицательное сальдо:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-194">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="a3fc7-195">Инструкция [`throw`](../language-reference/keywords/throw.md) **вызывает** исключение.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-195">The [`throw`](../language-reference/keywords/throw.md) statment **throws** an exception.</span></span> <span data-ttu-id="a3fc7-196">Когда будет найден соответствующий блок `catch`, выполнение текущего метода завершится и возобновится.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-196">Execution of the current method ends, and will resume when a matching `catch` block is found.</span></span> <span data-ttu-id="a3fc7-197">Вы добавите блок `catch` для тестирования этого кода немного позже.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-197">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="a3fc7-198">Чтобы вместо непосредственного обновления сальдо добавлялась начальная транзакция, конструктор должен получить одно изменение.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-198">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="a3fc7-199">Так как вы уже написали метод `MakeDeposit`, вызовите его из конструктора.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-199">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="a3fc7-200">Готовый конструктор должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-200">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="a3fc7-201"><xref:System.DateTime.Now?displayProperty=nameWithType> — это свойство, которое возвращает текущие дату и время.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-201"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="a3fc7-202">Протестируйте его, добавив несколько депозитов и списаний в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-202">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="a3fc7-203">Теперь протестируйте обнаружение условий ошибки. Для этого создайте счет с отрицательным сальдо:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-203">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive:
try {
    var invalidAccount = new BankAccount("invalid", -55);
} catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="a3fc7-204">С помощью [`try` и `catch` инструкций](../language-reference/keywords/try-catch.md) пометьте блок кода, который может вызывать исключения и обнаруживать потенциальные ошибки.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-204">You use the [`try` and `catch` statements](../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions, and to catch those errors that you expect.</span></span> <span data-ttu-id="a3fc7-205">Таким же образом можно протестировать код, который вызывает исключение в случае создания отрицательного сальдо:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-205">You can use the same technique to test the code that throws for a negative balance:</span></span>

```csharp
// Test for a negative balance
try {
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
} catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="a3fc7-206">Сохраните файл и введите `dotnet run` для проверки.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-206">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="a3fc7-207">Задача — регистрация всех транзакций</span><span class="sxs-lookup"><span data-stu-id="a3fc7-207">Challenge - log all transactions</span></span>

<span data-ttu-id="a3fc7-208">Чтобы завершить работу с этим кратким руководством, можно написать метод `GetAccountHistory`, который создает `string` для журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-208">To finish this quick start, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="a3fc7-209">Добавьте этот метод в тип `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-209">add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="a3fc7-210">В этом примере используется класс <xref:System.Text.StringBuilder>, чтобы отформатировать строку, которая содержит одну строку для каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-210">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="a3fc7-211">Код форматирования строки приведен выше в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-211">You've seen the string formatting code earlier in these quick starts.</span></span> <span data-ttu-id="a3fc7-212">В этом коде есть новый символ `\t`.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-212">One new character is `\t`.</span></span> <span data-ttu-id="a3fc7-213">Он позволяет вставить вкладку для форматирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-213">That inserts a tab to format the output.</span></span>

<span data-ttu-id="a3fc7-214">Добавьте следующую строку, чтобы проверить его в файле **Program.cs**:</span><span class="sxs-lookup"><span data-stu-id="a3fc7-214">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="a3fc7-215">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-215">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a3fc7-216">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a3fc7-216">Next Steps</span></span>

<span data-ttu-id="a3fc7-217">Если у вас возникли вопросы, см. оригинал этого руководства [в нашем репозитории GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/).</span><span class="sxs-lookup"><span data-stu-id="a3fc7-217">If you got stuck, you can see the source for this quick start [in our GitHub repo](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="a3fc7-218">Поздравляем! Вы выполнили задачи всех наших кратких руководств.</span><span class="sxs-lookup"><span data-stu-id="a3fc7-218">Congratulations, you've finished all our Quick Starts.</span></span> <span data-ttu-id="a3fc7-219">Если вы хотите узнать больше, обратитесь к нашим [руководствам](../tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="a3fc7-219">If you're eager to learn more, try our [tutorials](../tutorials/index.md)</span></span>
