---
title: Создание приложения Hello World на C# с помощью .NET Core в Visual Studio 2017
description: Узнайте, как создать простое консольное приложение .NET Core на C# с помощью Visual Studio 2017.
author: BillWagner
ms.author: wiwagn
ms.date: 09/13/2017
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: cc7d78006998b79fe9d522e71883ce1af817c051
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428558"
---
# <a name="build-a-c-hello-world-application-with-the-net-core-sdk-in-visual-studio-2017"></a>Создание приложения Hello World на C# с помощью пакета SDK для .NET Core в Visual Studio 2017

В этой статье описано, как выполнить сборку, отладку и публикацию простого консольного приложения .NET Core на C# с помощью Visual Studio 2017. Visual Studio 2017 предоставляет полнофункциональную среду для разработки приложений .NET Core. Если само приложение не имеет зависимостей от конкретной платформы, его можно выполнять на любой официально поддерживаемой платформе .NET Core и в любой системе, в которой установлена .NET Core.

## <a name="prerequisites"></a>Предварительные требования

[Visual Studio 2017 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core". Приложение можно разработать с помощью .NET Core версии 2.1 или выше.

Дополнительные сведения см. в статье [Зависимости и требования для .NET Core](../install/sdk.md?tabs=netcore30&pivots=os-windows#install-with-visual-studio).

## <a name="a-simple-hello-world-application"></a>Простое приложение Hello World

Для начала создадим простое консольное приложение Hello World. Выполните следующие действия.

1. Запустите Visual Studio. Выберите **Файл** > **Создать** > **Проект** в меню. В диалоговом окне **Новый проект** выберите узел **Visual C#** , а затем — узел **.NET Core**. Выберите шаблон проекта **Консольное приложение (.NET Core)** . В текстовом поле **Имя** введите "HelloWorld". Нажмите кнопку **OK**.

   ![Диалоговое окно создания проекта, в котором выбран шаблон проекта консольного приложения](./media/with-visual-studio/visual-studio-new-project.png)

1. Visual Studio использует шаблон для создания проекта. Шаблон консольного приложения C# для .NET Core автоматически определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>. `Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения. Все аргументы, предоставленные в командной строке при запуске приложения, доступны через массив *args*.

   ![Visual Studio и новый проект Hello World](./media/with-visual-studio/visual-studio-main-window.png)

   Этот шаблон создает простое приложение Hello World. Он вызывает метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> для отображения литеральной строки "Hello World!" в окне консоли. Запустите программу в режиме отладки, нажав на панели инструментов кнопку **HelloWorld** с зеленой стрелкой. Окно консоли появится на короткое время и затем сразу же закроется. Это происходит потому, что метод `Main` и приложение в целом завершаются сразу же, как только будет выполнена единственная инструкция в методе `Main`.

1. Чтобы приостановить приложение перед тем, как закроется окно консоли, добавьте следующий код сразу после вызова метода <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>:

   ```csharp
   Console.Write("Press any key to continue...");
   Console.ReadKey(true);
   ```

   Этот код предлагает пользователю нажать любую клавишу и приостанавливает работу программы до нажатия клавиши.

1. В строке меню выберите **Сборка** > **Собрать решение**. При этом программа компилируется в промежуточный язык IL, который затем преобразуется в двоичный код JIT-компилятором.

1. Запустите программу, нажав кнопку **HelloWorld** с зеленой стрелкой на панели инструментов.

   ![Окно консоли с приложением Hello World и надписью "Чтобы продолжить, нажмите любую клавишу"](./media/with-visual-studio/hello-world-console.png)

1. Для закрытия консольного окна нажмите любую клавишу.

## <a name="enhancing-the-hello-world-application"></a>Расширение приложения Hello World

Давайте расширим приложение. Теперь у пользователя будет запрашиваться имя, которое затем будет отображаться с датой и временем. Выполните следующие действия, чтобы изменить и протестировать программу.

1. Введите следующий код C# в окно редактирования кода между первой открывающей скобкой за строкой `static void Main(string[] args)` и первой закрывающей фигурной скобкой:

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   Этот код заменяет содержимое метода `Main`.

   ![Файл C# Visual Studio с обновленным методом Main](./media/with-visual-studio/visual-csharp-code-window.png)

   Теперь код выдает строку "What is your name?" (Как вас зовут?) в окно консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу ВВОД. Приложение сохраняет полученную строку в переменной с именем `name`. Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `date`. Наконец, с помощью [интерполированной строки](../../csharp/language-reference/tokens/interpolated.md) эти значения выводятся в окно консоли.

1. Скомпилируйте программу, выбрав действие **Сборка** > **Собрать решение**.

1. Запустите программу в режиме отладки, выбрав на панели инструментов кнопку с зеленой стрелкой, нажав клавишу F5 или выбрав пункт меню **Отладка** > **Начать отладку**. В ответ на приглашение в командной строке введите имя и нажмите клавишу ВВОД.

   ![Окно консоли с измененными выходными данными программы](./media/with-visual-studio/hello-world-update.png)

1. Для закрытия консольного окна нажмите любую клавишу.

Вы создали и запустили приложение. Чтобы приложение достигло профессионального уровня, нужно выполнить еще несколько шагов для подготовки приложения к выпуску:

- См. дополнительные сведения об [отладке приложения Hello World .NET Core в Visual Studio 2017](debugging-with-visual-studio.md).

- См. дополнительные сведения о [разработке и публикации распространяемой версии приложения Hello World .NET Core с помощью Visual Studio 2017](publishing-with-visual-studio.md).

## <a name="related-articles"></a>Связанные статьи

Вместо консольного приложения .NET Core и Visual Studio 2017 позволяют создать библиотеку классов. Пошаговое описание этого процесса вы найдете в статье [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md) (Создание библиотеки классов с помощью C# и .NET Core в Visual Studio 2017).

Для разработки консольных приложений .NET Core для Mac, Linux и Windows также можно использовать редактор кода [Visual Studio Code](https://code.visualstudio.com/). Пошаговые инструкции см. в статье [Getting Started with Visual Studio Code](with-visual-studio-code.md) (Приступая к работе с Visual Studio Code).
