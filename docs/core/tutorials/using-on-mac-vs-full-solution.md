---
title: Создание полноценного решения .NET Core с помощью Visual Studio для Mac
description: В этой статье описывается сборка решения .NET Core, включающего многократно используемую библиотеку и модульное тестирование.
ms.date: 12/19/2019
ms.openlocfilehash: 8c9fcca404a3875b6bb7f9cf20551a017ff553c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78239967"
---
# <a name="build-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a>Создание полноценного решения .NET Core на базе macOS с помощью Visual Studio для Mac

Visual Studio для Mac предоставляет полнофункциональную интегрированную среду для разработки приложений .NET Core. В этой статье описывается сборка решения .NET Core, включающего многократно используемую библиотеку и модульное тестирование.

В этом учебнике показано, как создать приложение, которое принимает искомое слово и строку текста от пользователя, с помощью метода из библиотеки классов, подсчитывает, сколько раз искомое слово встречается в строке, и возвращает результат пользователю. Это решение также включает модульное тестирование для библиотеки классов, позволяющее ознакомиться с основными концепциями модульного тестирования. Если при изучении руководства вы хотите использовать готовый пример, скачайте [его](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter). Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

> [!NOTE]
> Ваш отзыв очень важен. Вы можете отправить отзыв о Visual Studio для Mac команде разработчиков двумя способами.
>
> - В Visual Studio для Mac выберите пункт **Справка** > **Сообщить о проблеме** в меню или элемент **Сообщить о проблеме** на экране приветствия. При этом открывается окно для заполнения отчета об ошибках. Отслеживать свои отзывы можно на портале [сообщества разработчиков](https://developercommunity.visualstudio.com/spaces/41/index.html).
> - Чтобы внести предложение, выберите пункт **Справка** > **Отправить предложение** в меню или элемент **Отправить предложение** на экране приветствия. При этом откроется [веб-страница сообщества разработчиков Visual Studio для Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Предварительные требования

- [Пакет SDK для .NET Core 3.1 или более поздней версии](https://dotnet.microsoft.com/download).
- [Visual Studio 2019 для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).

Дополнительные сведения о предварительных требованиях см. в статье [Зависимости и требования для .NET Core](../install/dependencies.md?pivots=os-macos). Полный список требований к Visual Studio 2019 для Mac см. в статье [Требования к системе семейства продуктов Visual Studio 2019 для Mac](/visualstudio/productinfo/vs2019-system-requirements-mac).

## <a name="building-a-library"></a>Создание библиотеки

1. В окне запуска выберите **Создать проект**. В узле **.NET Core** диалогового окна **Создание проекта** выберите шаблон **Библиотека .NET Standard**. Эта команда создает библиотеку .NET Standard, предназначенную для .NET Core, а также любой другой реализации .NET, поддерживающей версию 2.1 [.NET Standard](../../standard/net-standard.md). Если установлено несколько версий пакета SDK для .NET Core, можно выбрать разные версии .NET Standard для библиотеки. Выберите .NET Standard 2.1 и нажмите кнопку **Далее**.

   > [!div class="mx-imgBorder"]
   > ![Диалоговое окно "Создание проекта" Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project.png)

1. Назовите проект "TextUtils" (сокращение от "Text Utilities"), а решение — "WordCounter". Оставьте флажок **Создайте каталог проекта в каталоге решения** установленным. Выберите **Создать**.

   > [!div class="mx-imgBorder"]
   > ![Параметры диалогового окна "Создание проекта" Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-options.png)

1. На панели **Решение** разверните узел `TextUtils`, чтобы отобразить предоставленный шаблоном файл класса *Class1.cs*. Удерживая нажатой клавишу CTRL, щелкните файл, выберите **Переименовать** в контекстном меню и переименуйте файл в *WordCount.cs*. Откройте файл и замените его содержимое на следующий код:

   [!code-csharp[Main](../../../samples/snippets/core/tutorials/using-on-mac-vs-full-solution/csharp/TextUtils/WordCount.cs)]

1. Сохраните файл любым из трех способов: используйте сочетание клавиш <kbd>&#8984;</kbd>+<kbd>S</kbd>, выберите **Файл** > **Сохранить** в меню или щелкните вкладку файла, удерживая нажатой клавишу CTRL, и выберите пункт **Сохранить** в контекстном меню. На следующем рисунке показано окно интегрированной среды разработки:

   > [!div class="mx-imgBorder"]
   > ![Окно интегрированной среды разработки Visual Studio для Mac с файлом и методом библиотеки классов](./media/using-on-mac-vs-full-solution/visual-studio-mac-editor.png)

1. Выберите **Ошибки** в нижней части окна интегрированной среды разработки, чтобы открыть панель **Ошибки**. Нажмите кнопку **Выходные данные сборки**.

   > [!div class="mx-imgBorder"]
   > ![Нижнее поле окна интегрированной среды разработки Visual Studio для Mac с кнопкой "Ошибки"](./media/using-on-mac-vs-full-solution/visual-studio-mac-error-button.png)

1. Выберите в меню **Сборка** > **Собрать все**.

   Выполняется сборка решения. На панели выходных данных отображается сообщение об успешной сборке.

   > [!div class="mx-imgBorder"]
   > ![Область выходных данных Visual Studio для Mac на панели "Ошибки" c сообщением об успешной сборке](./media/using-on-mac-vs-full-solution/visual-studio-mac-build-panel.png)

## <a name="creating-a-test-project"></a>Создание тестового проекта

Модульные тесты обеспечивают автоматическое тестирование программного обеспечения во время разработки и публикации. В этом учебнике используется платформа тестирования [xUnit (версии 2.4.0 или более поздней)](https://xunit.github.io/), которая автоматически устанавливается при добавлении тестового проекта xUnit в решение на следующих этапах:

1. На боковой панели **Решение** щелкните решение `WordCounter` при нажатой клавише CTRL и выберите пункт **Добавить** > **Добавить новый проект**.

1. В узле **.NET Core** диалогового окна **Создание проекта** выберите **Тесты**. Выберите **xUnit Test Project** (Тестовый проект xUnit) и нажмите кнопку **Далее**.

   > [!div class="mx-imgBorder"]
   > ![Создание тестового проекта xUnit в диалоговом окне "Создание проекта" Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-project.png)

1. При наличии нескольких версий пакета SDK для .NET Core необходимо выбрать версию для этого проекта. Выберите **.NET Core 3.1**. Назовите новый проект "TestLibrary" и выберите **Создать**.

   > [!div class="mx-imgBorder"]
   > ![Диалоговое окно "Создание проекта" Visual Studio для Mac с именем проекта](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-name.png)

1. Чтобы библиотека тестов работала с `WordCount`, добавьте ссылку на проект `TextUtils`. На боковой панели **Решение** щелкните элемент **Зависимости** при нажатой клавише CTRL в области **TestLibrary**. Выберите пункт **Изменить ссылки** в контекстном меню.

1. В диалоговом окне **Изменить ссылки** выберите проект **TextUtils** на вкладке **Проекты**. Нажмите кнопку **ОК**.

   > [!div class="mx-imgBorder"]
   > ![Диалоговое окно "Изменение ссылок" Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-edit-references.png)

1. В проекте **TestLibrary** переименуйте файл *UnitTest1.cs* в *TextUtilsTests.cs*.

1. Откройте файл и замените его содержимое на следующий код:

   ```csharp
   using Xunit;
   using TextUtils;
   using System.Diagnostics;

   namespace TestLibrary
   {
       public class TextUtils_GetWordCountShould
       {
           [Fact]
           public void IgnoreCasing()
           {
               var wordCount = WordCount.GetWordCount("Jack", "Jack jack");

               Assert.NotEqual(2, wordCount);
           }
       }
   }
   ```

   На следующем рисунке показана интегрированная среда разработки с кодом модульного тестирования. Обратите внимание на оператор `Assert.NotEqual`.

   > [!div class="mx-imgBorder"]
   > ![Начальный модульный тест Visual Studio для Mac в главном окне интегрированной среды разработки](./media/using-on-mac-vs-full-solution/visual-studio-mac-assert-test.png)

   Важно однократно выполнить новый тест так, чтобы он завершился со сбоем. Это позволяет проверить правильность его логики тестирования. Метод передает имя "Jack" (с прописной буквы) и строку, содержащую "Jack" и "jack" (с прописной и строчной буквы). Если метод `GetWordCount` работает правильно, он возвращает два вхождения искомого слова. Чтобы намеренно не пройти этот тест, сначала реализуйте тест, утверждающий, что методом `GetWordCount` не возвращаются два вхождения искомого слова "Jack". После этого перейдите к следующему шагу.

1. Откройте панель **Модульные тесты** в правой части экрана. В меню выберите **Просмотр** > **Тесты**.

   > [!div class="mx-imgBorder"]
   > ![Панель "Модульные тесты" в Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-panel.png)

1. Щелкните значок **Закрепить**, чтобы панель не закрывалась. (Выделено на следующем рисунке.)

   > [!div class="mx-imgBorder"]
   > ![Значок закрепления на панели "Модульные тесты" в Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-dock-icon.png)

1. Нажмите кнопку **Запустить все**.

   Тест завершается неудачно, что соответствует правильному результату. Метод теста утверждает, что два вхождения `inputString` — "Jack" — не возвращаются из строки "Jack jack", предоставленной методом `GetWordCount`. Так как регистр слов не учитывался в методе `GetWordCount`, возвращаются два экземпляра. Утверждение о том, что 2 *не равно* 2, приводит к ошибке. Это правильный результат, а значит логика нашего теста работает корректно.

   > [!div class="mx-imgBorder"]
   > ![Отображение сбоя теста в Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-for-mac-unit-test-failure.png)

1. Измените метод теста `IgnoreCasing`, изменив `Assert.NotEqual` на `Assert.Equal`. Чтобы сохранить файл, используйте сочетание клавиш <kbd>CTRL</kbd>+<kbd>S</kbd>, выберите в меню элементы **Файл** > **Сохранить** или щелкните вкладку файла при нажатой клавише CTRL и выберите пункт **Сохранить** в контекстном меню.

   Вы ожидаете, что `searchWord` "Jack" возвратит два вхождения при передаче `inputString` "Jack jack" в `GetWordCount`. Чтобы выполнить тест снова, нажмите кнопку **Выполнить тесты** на панели **Модульные тесты** или кнопку **Перезапустить тесты** на панели **Результаты теста** в нижней части экрана. Тест проходит. Существует два вхождения "Jack" в строке "Jack jack" (без учета регистра), а утверждение теста равно `true`.

   > [!div class="mx-imgBorder"]
   > ![Отображение прохождения теста в Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)

1. Тестирование отдельных возвращаемых значений с помощью `Fact` — это всего лишь азы модульного тестирования. Другая эффективная методика для проверки нескольких значений одновременно заключается в использовании `Theory`. Добавьте следующий метод в свой класс `TextUtils_GetWordCountShould`. Теперь ваш класс содержит два метода:

   ```csharp
   [Theory]
   [InlineData(0, "Ting", "Does not appear in the string.")]
   [InlineData(1, "Ting", "Ting appears once.")]
   [InlineData(2, "Ting", "Ting appears twice with Ting.")]
   public void CountInstancesCorrectly(int count,
                                       string searchWord,
                                       string inputString)
   {
       Assert.NotEqual(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   `CountInstancesCorrectly` проверяет, что метод `GetWordCount` ведет подсчет правильно. `InlineData` предоставляет счетчик, искомое слово и входную строку для проверки. Метод теста запускается один раз для каждой строки данных. Отметим еще раз, что сначала вы подтверждаете сбой с помощью `Assert.NotEqual`, даже если знаете, что счетчики в данных правильны, а значения будут соответствовать счетчикам, возвращаемым методом `GetWordCount`. Вначале может показаться, что такое намеренное непрохождение теста является пустой тратой времени, но подобная проверка логики тестов очень важна. Если вы столкнетесь с методом теста, при котором проверка проходит успешно, хотя такого быть не должно, это означает, что вы обнаружили ошибку в логике теста. Не стоит пренебрегать этим этапом при создании тестовых методов.

1. Сохраните файл и снова запустите тесты. Тест регистра проходит успешно, но три теста счетчиков завершаются неудачей. Именно этого мы и ожидаем.

   > [!div class="mx-imgBorder"]
   > ![Ожидаемый сбой теста в Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-failure.png)

1. Измените метод теста `CountInstancesCorrectly`, изменив `Assert.NotEqual` на `Assert.Equal`. Сохраните файл. Повторно запустите тесты. Все тесты пройдены.

   > [!div class="mx-imgBorder"]
   > ![Ожидаемое прохождение теста в Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)

## <a name="adding-a-console-app"></a>Добавление консольного приложения

1. На боковой панели **Решение** щелкните решение `WordCounter` при нажатой клавише CTRL. Добавьте новый проект **Консольное приложение**, выбрав шаблон в области **.NET Core** > **Приложение**. Выберите **Далее**. Присвойте проекту имя **WordCounterApp**. Выберите **Создать**, чтобы создать проект в решении.

1. На боковой панели **Решения** щелкните узел **Зависимости** нового проекта **WordCounterApp** при нажатой клавише CTRL. В диалоговом окне **Изменить ссылки** установите флажок **TextUtils** и нажмите кнопку **ОК**.

1. Откройте файл *Program.cs*. Замените код следующим кодом:

   [!code-csharp[Main](../../../samples/snippets/core/tutorials/using-on-mac-vs-full-solution/csharp/WordCounterApp/Program.cs)]

1. Удерживая нажатой клавишу CTRL, щелкните проект `WordCounterApp` и выберите **Запустить проект** в контекстном меню. При запуске приложения укажите значения для искомого слова и входной строки в окне консоли. Приложение указывает количество вхождений искомого слова в строке.

   > [!div class="mx-imgBorder"]
   > ![Окно консоли Visual Studio для Mac с отображением запуска приложения](./media/using-on-mac-vs-full-solution/visual-studio-mac-console-window.png)

1. Последней мы рассмотрим функцию отладки в Visual Studio для Mac. Установите точку останова в операторе `Console.WriteLine`. Выберите в левом поле строки 23 и рядом со строкой кода появится красный кружок. Можно также щелкнуть в любом месте строки кода и выбрать в меню **Выполнить** > **Перейти к следующей точке останова**.

   > [!div class="mx-imgBorder"]
   > ![Установленная точка останова Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-breakpoint.png)

1. Щелкните проект `WordCounterApp`, удерживая клавишу CTRL. Выберите **Начать отладку проекта** в контекстном меню. При запуске приложения введите искомое слово "cat", а также "The dog chased the cat, but the cat escaped" в качестве строки для поиска. При достижении оператора `Console.WriteLine` выполнение программы прекращается до выполнения этого оператора. На вкладке **Локальные** вы можете увидеть значения `searchWord`, `inputString`, `wordCount` и `pluralChar`.

   > [!div class="mx-imgBorder"]
   > ![Остановлено выполнение программы отладчика в Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-debugger.png)

1. В области **Интерпретация** введите "wordCount = 999;" и нажмите клавишу ВВОД. Эта команда присваивает переменной `wordCount` не имеющее смысла значение 999. Таким образом можно изменять значения переменных во время отладки.

   > [!div class="mx-imgBorder"]
   > ![Изменяемые значения Visual Studio для Mac в окне интерпретации](./media/using-on-mac-vs-full-solution/visual-studio-mac-immediate-window.png)

1. Щелкните стрелку *Продолжить* на панели инструментов. Взгляните на выходные данные в окне консоли. Там указано неправильное значение 999, заданное при отладке приложения.

   > [!div class="mx-imgBorder"]
   > ![Кнопка "Продолжить" в Visual Studio для Mac на панели инструментов](./media/using-on-mac-vs-full-solution/visual-studio-mac-toolbar.png)

   > [!div class="mx-imgBorder"]
   > ![Выходные данные в окне консоли Visual Studio для Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-output.png)

Вы можете использовать тот же процесс для отладки кода с помощью проекта модульного теста. Вместо запуска проекта приложения WordCount, щелкните проект **Библиотека тестов** при нажатой клавише CTRL и выберите **Начать отладку проекта** в контекстном меню. Visual Studio для Mac запускает тестовый проект с присоединенным отладчиком. Выполнение будет прервано в любой точке останова, добавленной в тестовый проект или базовый код библиотеки.

## <a name="see-also"></a>См. также

- [Заметки о выпуске Visual Studio 2019 для Mac](/visualstudio/releasenotes/vs2019-mac-relnotes)
