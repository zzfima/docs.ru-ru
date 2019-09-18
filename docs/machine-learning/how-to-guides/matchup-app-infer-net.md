---
title: Создание приложения со списком матчей с помощью Infer.NET и вероятностного программирования
description: Узнайте, как использовать вероятностное программирование и Infer.NET для создания приложения со списком матчей на основе упрощенной версии TrueSkill.
ms.date: 05/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: aa3ad9528238e4f5a5eb187af71f2d2da1ea9cba
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855785"
---
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a><span data-ttu-id="abf87-103">Создание приложения со списком матчей с помощью Infer.NET и вероятностного программирования</span><span class="sxs-lookup"><span data-stu-id="abf87-103">Create a game match up list app with Infer.NET and probabilistic programming</span></span>

<span data-ttu-id="abf87-104">Это руководство содержит сведения о вероятностном программировании с использованием Infer.NET.</span><span class="sxs-lookup"><span data-stu-id="abf87-104">This how-to guide teaches you about probabilistic programming using Infer.NET.</span></span> <span data-ttu-id="abf87-105">Вероятностное программирование — это метод машинного обучения, который позволяет выражать пользовательские модели в виде компьютерных программ.</span><span class="sxs-lookup"><span data-stu-id="abf87-105">Probabilistic programming is a machine learning approach where custom models are expressed as computer programs.</span></span> <span data-ttu-id="abf87-106">Он позволяет включить в модель знания о предметной области и делает систему машинного обучения более логичной и понятной.</span><span class="sxs-lookup"><span data-stu-id="abf87-106">It allows for incorporating domain knowledge in the models and makes the machine learning system more interpretable.</span></span> <span data-ttu-id="abf87-107">Также он поддерживает оперативный вывод, то есть обучение по мере поступления новых данных.</span><span class="sxs-lookup"><span data-stu-id="abf87-107">It also supports online inference – the process of learning as new data arrives.</span></span> <span data-ttu-id="abf87-108">Infer.NET используется в нескольких продуктах корпорации Майкрософт, например Azure, Xbox и Bing.</span><span class="sxs-lookup"><span data-stu-id="abf87-108">Infer.NET is used in various products at Microsoft in Azure, Xbox, and Bing.</span></span>

## <a name="what-is-probabilistic-programming"></a><span data-ttu-id="abf87-109">Что такое вероятностное программирование?</span><span class="sxs-lookup"><span data-stu-id="abf87-109">What is probabilistic programming?</span></span>

<span data-ttu-id="abf87-110">Вероятностное программирование позволяет создавать статистические модели для реальных процессов.</span><span class="sxs-lookup"><span data-stu-id="abf87-110">Probabilistic programming allows you to create statistical models of real-world processes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abf87-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="abf87-111">Prerequisites</span></span>

- <span data-ttu-id="abf87-112">Настройка локальной среды разработки</span><span class="sxs-lookup"><span data-stu-id="abf87-112">Local development environment setup</span></span>

  <span data-ttu-id="abf87-113">Для работы с этим руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="abf87-113">This how-to guide expects you to have a machine you can use for development.</span></span> <span data-ttu-id="abf87-114">В руководстве по [созданию программы Hello World за 10 минут](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) содержатся инструкции по настройке локальной среды разработки в macOS, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="abf87-114">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on macOS, Windows, or Linux.</span></span>

## <a name="create-your-app"></a><span data-ttu-id="abf87-115">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="abf87-115">Create your app</span></span>

1. <span data-ttu-id="abf87-116">Откройте новое окно командной строки и выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="abf87-116">Open a new command prompt and run the following commands:</span></span>

```console
dotnet new console -o myApp
cd myApp
```

<span data-ttu-id="abf87-117">Команда `dotnet` создает приложение `new` с типом `console`.</span><span class="sxs-lookup"><span data-stu-id="abf87-117">The `dotnet` command creates a `new` application of type `console`.</span></span> <span data-ttu-id="abf87-118">Параметр `-o` создает каталог с именем `myApp`, в котором хранится само приложение и используемые им файлы.</span><span class="sxs-lookup"><span data-stu-id="abf87-118">The `-o` parameter creates a directory named `myApp` where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="abf87-119">Команда `cd myApp` переносит вас в только что созданный каталог приложения.</span><span class="sxs-lookup"><span data-stu-id="abf87-119">The `cd myApp` command puts you into the newly created app directory.</span></span>

## <a name="install-infernet-package"></a><span data-ttu-id="abf87-120">Установка пакета Infer.NET</span><span class="sxs-lookup"><span data-stu-id="abf87-120">Install Infer.NET package</span></span>

<span data-ttu-id="abf87-121">Чтобы использовать Infer.NET, необходимо установить пакет `Microsoft.ML.Probabilistic.Compiler`.</span><span class="sxs-lookup"><span data-stu-id="abf87-121">To use Infer.NET, you need to install the `Microsoft.ML.Probabilistic.Compiler` package.</span></span> <span data-ttu-id="abf87-122">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="abf87-122">In your command prompt, run the following command:</span></span>

```console
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a><span data-ttu-id="abf87-123">Разработка модели</span><span class="sxs-lookup"><span data-stu-id="abf87-123">Design your model</span></span>

<span data-ttu-id="abf87-124">Этот пример использует таблицу проведенных в офисе компании матчей по настольному теннису или кикеру.</span><span class="sxs-lookup"><span data-stu-id="abf87-124">The example sample uses table tennis or foosball matches played in the office.</span></span> <span data-ttu-id="abf87-125">Для каждого матча указаны участники и результаты.</span><span class="sxs-lookup"><span data-stu-id="abf87-125">You have the participants and outcome of each match.</span></span>  <span data-ttu-id="abf87-126">Теперь на основе этих данных вы можете определить навыки каждого игрока.</span><span class="sxs-lookup"><span data-stu-id="abf87-126">You want to infer the player's skills from this data.</span></span> <span data-ttu-id="abf87-127">Предположим, что каждый игрок обладает навыком с нормальным распределением, а его результаты в матчах определяются значением этого навыка с наложением некоторого шума.</span><span class="sxs-lookup"><span data-stu-id="abf87-127">Assume that each player has a normally distributed latent skill and their given match performance is a noisy version of this skill.</span></span> <span data-ttu-id="abf87-128">Данные определяют ограничения для результатов игрока: у победителя они должны быть выше, чем у проигравшего.</span><span class="sxs-lookup"><span data-stu-id="abf87-128">The data constrains the winner’s performance to be greater than the loser’s performance.</span></span> <span data-ttu-id="abf87-129">Это упрощенная версия популярной модели [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/), которая также поддерживает группы поддержки, ничьи и другие расширения.</span><span class="sxs-lookup"><span data-stu-id="abf87-129">This is a simplified version of the popular [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/) model, which also supports teams, draws, and other extensions.</span></span> <span data-ttu-id="abf87-130">[Расширенная версия](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) этой модели используется для сопоставления игроков в популярных играх Halo и Gears of War.</span><span class="sxs-lookup"><span data-stu-id="abf87-130">An [advanced version](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) of this model is used for matchmaking in the best-selling game titles Halo and Gears of War.</span></span>

<span data-ttu-id="abf87-131">Вам нужно получить список игроков с оценкой значения навыка и неопределенности этого значения.</span><span class="sxs-lookup"><span data-stu-id="abf87-131">You need to list the inferred player skills, alongside with their variance – the measure of uncertainty around the skills.</span></span>

<span data-ttu-id="abf87-132">*Пример данных о результатах игр*</span><span class="sxs-lookup"><span data-stu-id="abf87-132">*Game result sample data*</span></span>

<span data-ttu-id="abf87-133">Игра</span><span class="sxs-lookup"><span data-stu-id="abf87-133">Game</span></span> |<span data-ttu-id="abf87-134">Победитель</span><span class="sxs-lookup"><span data-stu-id="abf87-134">Winner</span></span> | <span data-ttu-id="abf87-135">Проигравший</span><span class="sxs-lookup"><span data-stu-id="abf87-135">Loser</span></span>
---------|----------|---------
 <span data-ttu-id="abf87-136">1</span><span class="sxs-lookup"><span data-stu-id="abf87-136">1</span></span> | <span data-ttu-id="abf87-137">Игрок 0</span><span class="sxs-lookup"><span data-stu-id="abf87-137">Player 0</span></span> | <span data-ttu-id="abf87-138">Игрок 1</span><span class="sxs-lookup"><span data-stu-id="abf87-138">Player 1</span></span>
 <span data-ttu-id="abf87-139">2</span><span class="sxs-lookup"><span data-stu-id="abf87-139">2</span></span> | <span data-ttu-id="abf87-140">Игрок 0</span><span class="sxs-lookup"><span data-stu-id="abf87-140">Player 0</span></span> | <span data-ttu-id="abf87-141">Игрок 3</span><span class="sxs-lookup"><span data-stu-id="abf87-141">Player 3</span></span>
 <span data-ttu-id="abf87-142">3</span><span class="sxs-lookup"><span data-stu-id="abf87-142">3</span></span> | <span data-ttu-id="abf87-143">Игрок 0</span><span class="sxs-lookup"><span data-stu-id="abf87-143">Player 0</span></span> | <span data-ttu-id="abf87-144">Игрок 4</span><span class="sxs-lookup"><span data-stu-id="abf87-144">Player 4</span></span>
 <span data-ttu-id="abf87-145">4</span><span class="sxs-lookup"><span data-stu-id="abf87-145">4</span></span> | <span data-ttu-id="abf87-146">Игрок 1</span><span class="sxs-lookup"><span data-stu-id="abf87-146">Player 1</span></span> | <span data-ttu-id="abf87-147">Игрок 2</span><span class="sxs-lookup"><span data-stu-id="abf87-147">Player 2</span></span>
 <span data-ttu-id="abf87-148">5</span><span class="sxs-lookup"><span data-stu-id="abf87-148">5</span></span> | <span data-ttu-id="abf87-149">Игрок 3</span><span class="sxs-lookup"><span data-stu-id="abf87-149">Player 3</span></span> | <span data-ttu-id="abf87-150">Игрок 1</span><span class="sxs-lookup"><span data-stu-id="abf87-150">Player 1</span></span>
 <span data-ttu-id="abf87-151">6</span><span class="sxs-lookup"><span data-stu-id="abf87-151">6</span></span> | <span data-ttu-id="abf87-152">Игрок 4</span><span class="sxs-lookup"><span data-stu-id="abf87-152">Player 4</span></span> | <span data-ttu-id="abf87-153">Игрок 2</span><span class="sxs-lookup"><span data-stu-id="abf87-153">Player 2</span></span>

<span data-ttu-id="abf87-154">Изучив эти данные, вы заметите, что у игроков 3 и 4 есть по одной победе и одному поражению.</span><span class="sxs-lookup"><span data-stu-id="abf87-154">With a closer look at the sample data, you’ll notice that players 3 and 4 both have one win and one loss.</span></span> <span data-ttu-id="abf87-155">Давайте узнаем, какие оценки они получат по методу вероятностного программирования.</span><span class="sxs-lookup"><span data-stu-id="abf87-155">Let's see what the rankings look like using probabilistic programming.</span></span> <span data-ttu-id="abf87-156">Заметьте, что даже в офисных матчах нумерация игроков начинается с 0.</span><span class="sxs-lookup"><span data-stu-id="abf87-156">Notice also there is a player zero because even office match up lists are zero based to us developers.</span></span>

## <a name="write-some-code"></a><span data-ttu-id="abf87-157">Написание кода</span><span class="sxs-lookup"><span data-stu-id="abf87-157">Write some code</span></span>

<span data-ttu-id="abf87-158">Итак, мы создали модель, которую теперь можно выразить в виде вероятностной программы с помощью API-интерфейса Infer.NET для моделирования.</span><span class="sxs-lookup"><span data-stu-id="abf87-158">Having designed the model, it’s time to express it as a probabilistic program using the Infer.NET modeling API.</span></span> <span data-ttu-id="abf87-159">Откройте `Program.cs` в любом текстовом редакторе и замените все его содержимое следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="abf87-159">Open `Program.cs` in your favorite text editor and replace all of its contents with the following code:</span></span>

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

## <a name="run-your-app"></a><span data-ttu-id="abf87-160">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="abf87-160">Run your app</span></span>

<span data-ttu-id="abf87-161">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="abf87-161">In your command prompt, run the following command:</span></span>

```console
dotnet run
```

## <a name="results"></a><span data-ttu-id="abf87-162">Результаты</span><span class="sxs-lookup"><span data-stu-id="abf87-162">Results</span></span>

<span data-ttu-id="abf87-163">Результаты выполнения должны выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="abf87-163">Your results should be similar to the following:</span></span>

```
Compiling model...done.
Iterating:
.........|.........|.........|.........|.........| 50
Player 0 skill: Gaussian(9.517, 3.926)
Player 3 skill: Gaussian(6.834, 3.892)
Player 4 skill: Gaussian(6.054, 4.731)
Player 1 skill: Gaussian(4.955, 3.503)
Player 2 skill: Gaussian(2.639, 4.288)
```

<span data-ttu-id="abf87-164">Как вы видите, в результатах применения нашей модели игрок 3 расположен немного выше, чем игрок 4.</span><span class="sxs-lookup"><span data-stu-id="abf87-164">In the results, notice that player 3 ranks slightly higher than player 4 according to our model.</span></span> <span data-ttu-id="abf87-165">Это связано с тем, что победа игрока 3 над игроком 1 гораздо важнее, чем победа игрока 4 над игроком 2, ведь игрок 1 в своем матче обыграл игрока 2.</span><span class="sxs-lookup"><span data-stu-id="abf87-165">That’s because the victory of player 3 over player 1 is more significant than the victory of player 4 over player 2 – note that player 1 beats player 2.</span></span> <span data-ttu-id="abf87-166">Но несомненным чемпионом стал игрок 0!</span><span class="sxs-lookup"><span data-stu-id="abf87-166">Player 0 is the overall champ!</span></span>

## <a name="keep-learning"></a><span data-ttu-id="abf87-167">Продолжение обучения</span><span class="sxs-lookup"><span data-stu-id="abf87-167">Keep learning</span></span>

<span data-ttu-id="abf87-168">Разработка статистических моделей является важным навыком.</span><span class="sxs-lookup"><span data-stu-id="abf87-168">Designing statistical models is a skill on its own.</span></span> <span data-ttu-id="abf87-169">Команда исследователей корпорации Майкрософт из Кембриджа подготовила [бесплатную онлайн-книгу](http://mbmlbook.com/), которая служит своеобразным введением к этой статье.</span><span class="sxs-lookup"><span data-stu-id="abf87-169">The Microsoft Research Cambridge team has written a [free online book](http://mbmlbook.com/), which gives a gentle introduction to the article.</span></span> <span data-ttu-id="abf87-170">В главе 3 этой книги модель TrueSkill рассматривается более подробно.</span><span class="sxs-lookup"><span data-stu-id="abf87-170">Chapter 3 of this book covers the TrueSkill model in more detail.</span></span> <span data-ttu-id="abf87-171">Придумав свою модель, преобразуйте ее в код с помощью [подробной документации](https://dotnet.github.io/infer/) на веб-сайте Infer.NET.</span><span class="sxs-lookup"><span data-stu-id="abf87-171">Once you have a model in mind, you can transform it into code using the [extensive documentation](https://dotnet.github.io/infer/) on the Infer.NET website.</span></span>

## <a name="next-steps"></a><span data-ttu-id="abf87-172">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="abf87-172">Next steps</span></span>

<span data-ttu-id="abf87-173">Изучите наш репозиторий на GitHub, чтобы продолжить обучение и получить дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="abf87-173">Check out the Infer.NET GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="abf87-174">Репозиторий dotnet/infer на сайте GitHub</span><span class="sxs-lookup"><span data-stu-id="abf87-174">dotnet/infer GitHub repository</span></span>](https://github.com/dotnet/infer)
