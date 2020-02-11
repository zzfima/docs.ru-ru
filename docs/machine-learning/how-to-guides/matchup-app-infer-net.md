---
title: Приложение со списком матчей Infer.NET — вероятностное программирование
description: Узнайте, как использовать вероятностное программирование и Infer.NET для создания приложения со списком матчей на основе упрощенной версии TrueSkill.
ms.date: 01/30/2020
ms.custom: mvc,how-to
ms.openlocfilehash: 8e489d61c5e6cca53ba12b13fddd0b73c7f85ef9
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092607"
---
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a>Создание приложения со списком матчей с помощью Infer.NET и вероятностного программирования

Это руководство содержит сведения о вероятностном программировании с использованием Infer.NET. Вероятностное программирование — это метод машинного обучения, который позволяет выражать пользовательские модели в виде компьютерных программ. Он позволяет включить в модель знания о предметной области и делает систему машинного обучения более логичной и понятной. Также он поддерживает оперативный вывод, то есть обучение по мере поступления новых данных. Infer.NET используется в нескольких продуктах корпорации Майкрософт, например Azure, Xbox и Bing.

## <a name="what-is-probabilistic-programming"></a>Что такое вероятностное программирование?

Вероятностное программирование позволяет создавать статистические модели для реальных процессов.

## <a name="prerequisites"></a>Предварительные требования

- Настройка локальной среды разработки

  Для работы с этим руководством вам потребуется компьютер, который можно использовать для разработки. В руководстве по [созданию программы Hello World за 10 минут](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) содержатся инструкции по настройке локальной среды разработки в macOS, Windows или Linux.

## <a name="create-your-app"></a>Создание приложения

1. Откройте новое окно командной строки и выполните следующие команды:

```dotnetcli
dotnet new console -o myApp
cd myApp
```

Команда `dotnet` создает приложение `new` с типом `console`. Параметр `-o` создает каталог с именем `myApp`, в котором хранится само приложение и используемые им файлы. Команда `cd myApp` переносит вас в только что созданный каталог приложения.

## <a name="install-infernet-package"></a>Установка пакета Infer.NET

Чтобы использовать Infer.NET, необходимо установить пакет `Microsoft.ML.Probabilistic.Compiler`. В командной строке выполните следующую команду:

```dotnetcli
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a>Разработка модели

Этот пример использует таблицу проведенных в офисе компании матчей по настольному теннису или кикеру. Для каждого матча указаны участники и результаты.  Теперь на основе этих данных вы можете определить навыки каждого игрока. Предположим, что каждый игрок обладает навыком с нормальным распределением, а его результаты в матчах определяются значением этого навыка с наложением некоторого шума. Данные определяют ограничения для результатов игрока: у победителя они должны быть выше, чем у проигравшего. Это упрощенная версия популярной модели [TrueSkill](https://www.microsoft.com/research/project/trueskill-ranking-system/), которая также поддерживает группы поддержки, ничьи и другие расширения. [Расширенная версия](https://www.microsoft.com/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) этой модели используется для сопоставления игроков в популярных играх Halo и Gears of War.

Вам нужно получить список игроков с оценкой значения навыка и неопределенности этого значения.

*Пример данных о результатах игр*

Игра |Победитель | Проигравший
---------|----------|---------
 1 | Игрок 0 | Игрок 1
 2 | Игрок 0 | Игрок 3
 3 | Игрок 0 | Игрок 4
 4 | Игрок 1 | Игрок 2
 5 | Игрок 3 | Игрок 1
 6 | Игрок 4 | Игрок 2

Изучив эти данные, вы заметите, что у игроков 3 и 4 есть по одной победе и одному поражению. Давайте узнаем, какие оценки они получат по методу вероятностного программирования. Заметьте, что даже в офисных матчах нумерация игроков начинается с 0.

## <a name="write-some-code"></a>Написание кода

Итак, мы создали модель, которую теперь можно выразить в виде вероятностной программы с помощью API-интерфейса Infer.NET для моделирования. Откройте `Program.cs` в любом текстовом редакторе и замените все его содержимое следующим кодом:

```csharp
namespace myApp

{
    using System;
    using System.Linq;
    using Microsoft.ML.Probabilistic;
    using Microsoft.ML.Probabilistic.Distributions;
    using Microsoft.ML.Probabilistic.Models;

    class Program
    {

        static void Main(string[] args)
        {
            // The winner and loser in each of 6 samples games
            var winnerData = new[] { 0, 0, 0, 1, 3, 4 };
            var loserData = new[] { 1, 3, 4, 2, 1, 2 };

            // Define the statistical model as a probabilistic program
            var game = new Range(winnerData.Length);
            var player = new Range(winnerData.Concat(loserData).Max() + 1);
            var playerSkills = Variable.Array<double>(player);
            playerSkills[player] = Variable.GaussianFromMeanAndVariance(6, 9).ForEach(player);

            var winners = Variable.Array<int>(game);
            var losers = Variable.Array<int>(game);

            using (Variable.ForEach(game))
            {
                // The player performance is a noisy version of their skill
                var winnerPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[winners[game]], 1.0);
                var loserPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[losers[game]], 1.0);

                // The winner performed better in this game
                Variable.ConstrainTrue(winnerPerformance > loserPerformance);
            }

            // Attach the data to the model
            winners.ObservedValue = winnerData;
            losers.ObservedValue = loserData;

            // Run inference
            var inferenceEngine = new InferenceEngine();
            var inferredSkills = inferenceEngine.Infer<Gaussian[]>(playerSkills);

            // The inferred skills are uncertain, which is captured in their variance
            var orderedPlayerSkills = inferredSkills
               .Select((s, i) => new { Player = i, Skill = s })
               .OrderByDescending(ps => ps.Skill.GetMean());

            foreach (var playerSkill in orderedPlayerSkills)
            {
                Console.WriteLine($"Player {playerSkill.Player} skill: {playerSkill.Skill}");
            }
        }
    }
}
```

## <a name="run-your-app"></a>Запуск приложения

В командной строке выполните следующую команду:

```dotnetcli
dotnet run
```

## <a name="results"></a>Результаты

Результаты выполнения должны выглядеть примерно так:

```console
Compiling model...done.
Iterating:
.........|.........|.........|.........|.........| 50
Player 0 skill: Gaussian(9.517, 3.926)
Player 3 skill: Gaussian(6.834, 3.892)
Player 4 skill: Gaussian(6.054, 4.731)
Player 1 skill: Gaussian(4.955, 3.503)
Player 2 skill: Gaussian(2.639, 4.288)
```

Как вы видите, в результатах применения нашей модели игрок 3 расположен немного выше, чем игрок 4. Это связано с тем, что победа игрока 3 над игроком 1 гораздо важнее, чем победа игрока 4 над игроком 2, ведь игрок 1 в своем матче обыграл игрока 2. Но несомненным чемпионом стал игрок 0!

## <a name="keep-learning"></a>Продолжение обучения

Разработка статистических моделей является важным навыком. Команда исследователей корпорации Майкрософт из Кембриджа подготовила [бесплатную онлайн-книгу](http://mbmlbook.com/), которая служит своеобразным введением к этой статье. В главе 3 этой книги модель TrueSkill рассматривается более подробно. Придумав свою модель, преобразуйте ее в код с помощью [подробной документации](https://dotnet.github.io/infer/) на веб-сайте Infer.NET.

## <a name="next-steps"></a>Следующие шаги

Изучите наш репозиторий на GitHub, чтобы продолжить обучение и получить дополнительные примеры.
> [!div class="nextstepaction"]
> [Репозиторий dotnet/infer на сайте GitHub](https://github.com/dotnet/infer)
