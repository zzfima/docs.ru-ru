---
title: Создание приложения .NET Core Hello World на Visual Basic в Visual Studio 2017
description: Узнайте, как создать простое консольное приложение .NET Core на Visual Basic с помощью Visual Studio 2017.
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 612de47c4d40d1272eb330a0343302109040f434
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149385"
---
# <a name="build-a-net-core-visual-basic-hello-world-application-in-visual-studio-2017"></a>Создание приложения .NET Core Hello World на Visual Basic в Visual Studio 2017

В этой статье содержится пошаговое описание процессов сборки, отладки и публикации простого консольного приложения .NET Core на Visual Basic с помощью Visual Studio 2017. Visual Studio 2017 предоставляет полнофункциональную среду для разработки приложений .NET Core. Если само приложение не имеет зависимостей от конкретной платформы, его можно выполнять на любой официально поддерживаемой платформе .NET Core и в любой системе, в которой установлена .NET Core.

## <a name="prerequisites"></a>Предварительные требования

[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core". Приложение можно разработать с помощью .NET Core 2.0.

Дополнительные сведения см. в разделе [Необходимые компоненты для .NET Core в Windows](../../core/windows-prerequisites.md).

## <a name="a-simple-hello-world-application"></a>Простое приложение Hello World

Для начала создадим простое консольное приложение Hello World. Выполните следующие действия.

1. Запустите Visual Studio 2017. Выберите **Файл** > **Создать** > **Проект** в меню. В диалоговом окне *Новый проект* * выберите узел **Visual Basic**, а затем — узел **.NET Core**. Выберите шаблон проекта **Консольное приложение (.NET Core)**. В текстовом поле **Имя** введите "HelloWorld". Нажмите кнопку **OK**.

   ![Диалоговое окно создания проекта, в котором выбран шаблон проекта консольного приложения](./media/vb-with-visual-studio/new-project.png)
   
1. Visual Studio использует шаблон для создания проекта. Шаблон консольного приложения Visual Basic для .NET Core автоматически определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>. `Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения. Все аргументы, предоставленные в командной строке при запуске приложения, доступны через массив *args*.

   ![Visual Studio и новый проект Hello World](./media/vb-with-visual-studio/devenv.png)

   Этот шаблон создает простое приложение Hello World. Он вызывает метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> для отображения литеральной строки "Hello World!" в окне консоли. Запустите программу в режиме отладки, нажав на панели инструментов кнопку **HelloWorld** с зеленой стрелкой. Окно консоли появится на короткое время и затем сразу же закроется. Это происходит потому, что метод `Main` и приложение в целом завершаются сразу же, как только будет выполнена единственная инструкция в методе `Main`.

1. Чтобы приостановить приложение перед тем, как закроется окно консоли, добавьте следующий код сразу после вызова метода <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>:

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   Этот код предлагает пользователю нажать любую клавишу и приостанавливает работу программы до нажатия клавиши.

1. В строке меню выберите **Сборка** > **Собрать решение**. При этом программа компилируется в промежуточный язык IL, который затем преобразуется в двоичный код JIT-компилятором.

1. Запустите программу, нажав кнопку **HelloWorld** с зеленой стрелкой на панели инструментов.

   ![Окно консоли с приложением Hello World и надписью "Чтобы продолжить, нажмите любую клавишу"](./media/with-visual-studio/helloworld1.png)

1. Для закрытия консольного окна нажмите любую клавишу.

## <a name="enhancing-the-hello-world-application"></a>Расширение приложения Hello World

Давайте расширим приложение. Теперь у пользователя будет запрашиваться имя, которое затем будет отображаться с датой и временем. Выполните следующие действия, чтобы изменить и протестировать программу.

1. Введите следующий код Visual Basic в окне редактирования кода между первой открывающей скобкой за строкой `Sub Main(args As String())` и первой закрывающей скобкой:

   [!code-vb[GettingStarted#1](../../../samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   Этот код заменяет существующие операторы <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, <xref:System.Console.Write%2A?displayProperty=nameWithType> и <xref:System.Console.ReadKey%2A?displayProperty=nameWithType>.

   ![Файл программы Visual Studio с обновленным методом Main](./media/vb-with-visual-studio/codewindow.png)

   Теперь код выдает строку "What is your name?" (Как вас зовут?) в окно консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу ВВОД. Приложение сохраняет полученную строку в переменной с именем `name`. Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `currentDate`. Наконец, с помощью [интерполированной строки](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) эти значения выводятся в окно консоли.

1. Скомпилируйте программу, выбрав действие **Сборка** > **Собрать решение**.

1. Запустите программу в режиме отладки, выбрав на панели инструментов кнопку с зеленой стрелкой, нажав клавишу F5 или выбрав пункт меню **Отладка** > **Начать отладку**. В ответ на приглашение в командной строке введите имя и нажмите клавишу ВВОД.

   ![Окно консоли с измененными выходными данными программы](./media/with-visual-studio/helloworld2.png)

1. Для закрытия консольного окна нажмите любую клавишу.

Вы создали и запустили приложение. Чтобы приложение достигло профессионального уровня, нужно выполнить еще несколько шагов для подготовки приложения к выпуску:

- Сведения об отладке приложения см. в разделе [Отладка приложения Hello World на C# в Visual Studio 2017](debugging-with-visual-studio.md).

- Сведения о разработке и публикации распространяемой версии приложения см. в разделе [Публикация приложения Hello World на C# с помощью Visual Studio 2017](publishing-with-visual-studio.md).

<!--
## Related topics

Instead of a console application, you can also build a class library with .NET Core and Visual Studio 2017. For a step-by-step introduction, see [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md).

You can also develop a .NET Core console app on Mac, Linux, and Windows by using [Visual Studio Code](https://code.visualstudio.com/), a downloadable code editor. For a step-by-step tutorial, see [Getting Started with Visual Studio Code](with-visual-studio-code.md). -->
