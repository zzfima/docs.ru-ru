---
title: Учебник. Повторное обучение классификатора изображений TensorFlow (передача обучения)
description: Из этой статьи вы узнаете, как повторно обучить модель TensorFlow для классификации изображений с помощью передачи обучения и ML.NET. Исходная модель была обучена для классификации отдельных изображений. После повторного обучения новая модель сортирует изображения по различным категориям.
ms.date: 06/12/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 9344d0757e140995dfd9ce7d1a355910a81c6d31
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539854"
---
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a><span data-ttu-id="32fd8-105">Учебник. Повторное обучение классификатора изображений TensorFlow с помощью передачи обучения и ML.NET</span><span class="sxs-lookup"><span data-stu-id="32fd8-105">Tutorial: Retrain a TensorFlow image classifier with transfer learning and ML.NET</span></span>

<span data-ttu-id="32fd8-106">Из этой статьи вы узнаете, как повторно обучить модель TensorFlow для классификации изображений с помощью передачи обучения и ML.NET.</span><span class="sxs-lookup"><span data-stu-id="32fd8-106">Learn how to retrain an image classification TensorFlow model with transfer learning and ML.NET.</span></span> <span data-ttu-id="32fd8-107">Исходная модель была обучена для классификации отдельных изображений.</span><span class="sxs-lookup"><span data-stu-id="32fd8-107">The original model was trained to classify individual images.</span></span> <span data-ttu-id="32fd8-108">После повторного обучения новая модель сортирует изображения по различным категориям.</span><span class="sxs-lookup"><span data-stu-id="32fd8-108">After retraining, the new model organizes the images into broad categories.</span></span> 

<span data-ttu-id="32fd8-109">Обучение модели для [классификации изображений](https://en.wikipedia.org/wiki/Outline_of_object_recognition) с нуля предусматривает настройку нескольких миллионов параметров, а также использование огромных объемов помеченных данных обучения и вычислительных ресурсов (сотни часов работы GPU).</span><span class="sxs-lookup"><span data-stu-id="32fd8-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="32fd8-110">Хотя передача обучения не настолько эффективна, как обучение пользовательской модели с нуля, этот подход позволяет значительно ускорить соответствующий процесс с использованием всего нескольких тысяч изображений (а не миллионов помеченных изображений) для быстрого создания пользовательской модели (в пределах часа на компьютере без GPU).</span><span class="sxs-lookup"><span data-stu-id="32fd8-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span>

<span data-ttu-id="32fd8-111">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="32fd8-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="32fd8-112">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="32fd8-112">Understand the problem</span></span>
> * <span data-ttu-id="32fd8-113">повторно использовать и настраивать предварительно обученную модель;</span><span class="sxs-lookup"><span data-stu-id="32fd8-113">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="32fd8-114">классифицировать изображения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-114">Classify Images</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="32fd8-115">Что собой представляет передача обучения?</span><span class="sxs-lookup"><span data-stu-id="32fd8-115">What is transfer learning?</span></span>

<span data-ttu-id="32fd8-116">Хотели ли бы вы иметь возможность повторно использовать предварительно обученную модель для решения похожей проблемы, а также переобучать для этой цели все или некоторые слои такой модели?</span><span class="sxs-lookup"><span data-stu-id="32fd8-116">What if you could reuse a model that's already been pre trained to solve a similar problem and retrain either all or some of the layers of that model to make it solve your problem?</span></span> <span data-ttu-id="32fd8-117">Подход с повторным использованием части уже обученной модели для создания новой называется [передачей обучения](https://en.wikipedia.org/wiki/Transfer_learning).</span><span class="sxs-lookup"><span data-stu-id="32fd8-117">This technique of reusing part of an already trained model to build a new model is known as [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning).</span></span>

## <a name="image-classification-sample-overview"></a><span data-ttu-id="32fd8-118">Пример классификации изображений</span><span class="sxs-lookup"><span data-stu-id="32fd8-118">Image classification sample overview</span></span>

<span data-ttu-id="32fd8-119">Этот пример представляет собой консольное приложение, которое использует ML.NET для создания классификатора изображений путем повторного применения предварительно обученной модели для классификации изображений на основе небольшого объема данных обучения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-119">The sample is a console application that uses ML.NET to build an image classifier by reusing a pre-trained model to classify images with a small amount of training data.</span></span>

<span data-ttu-id="32fd8-120">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="32fd8-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="32fd8-121">Обратите внимание на то, что по умолчанию конфигурации проекта .NET в этом руководстве предназначена для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="32fd8-121">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="32fd8-122">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="32fd8-122">Prerequisites</span></span>

* <span data-ttu-id="32fd8-123">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="32fd8-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span> 

* <span data-ttu-id="32fd8-124">Пакет Nuget для Microsoft.ML 1.0.0.</span><span class="sxs-lookup"><span data-stu-id="32fd8-124">Microsoft.ML 1.0.0 Nuget package</span></span>
* <span data-ttu-id="32fd8-125">Пакет Nuget для Microsoft.ML.ImageAnalytics 1.0.0.</span><span class="sxs-lookup"><span data-stu-id="32fd8-125">Microsoft.ML.ImageAnalytics 1.0.0 Nuget package</span></span>
* <span data-ttu-id="32fd8-126">Пакет Nuget для Microsoft.ML.TensorFlow 0.12.0.</span><span class="sxs-lookup"><span data-stu-id="32fd8-126">Microsoft.ML.TensorFlow 0.12.0 Nuget package</span></span>

* [<span data-ttu-id="32fd8-127">ZIP-файл каталога ресурсов руководства.</span><span class="sxs-lookup"><span data-stu-id="32fd8-127">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="32fd8-128">Модель машинного обучения Inception версии 3.</span><span class="sxs-lookup"><span data-stu-id="32fd8-128">The InceptionV3 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="32fd8-129">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="32fd8-129">Select the appropriate machine learning task</span></span>

<span data-ttu-id="32fd8-130">[Глубокое обучение](https://en.wikipedia.org/wiki/Deep_learning) — это разновидность машинного обучения, которая произвела революцию в области компьютерного зрения и распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="32fd8-130">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="32fd8-131">Модели глубокого обучения обучаются на крупных наборах [помеченных данных](https://en.wikipedia.org/wiki/Labeled_data) с использованием [нейронных сетей](https://en.wikipedia.org/wiki/Artificial_neural_network), которые содержат множество слоев обучения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-131">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="32fd8-132">Глубокое обучение:</span><span class="sxs-lookup"><span data-stu-id="32fd8-132">Deep learning:</span></span>

* <span data-ttu-id="32fd8-133">лучше выполняет некоторые задачи, например в области компьютерного зрения;</span><span class="sxs-lookup"><span data-stu-id="32fd8-133">Performs better on some tasks like Computer Vision.</span></span>

* <span data-ttu-id="32fd8-134">хорошо работает с огромными объемами данных.</span><span class="sxs-lookup"><span data-stu-id="32fd8-134">Performs well on huge data amounts.</span></span>

<span data-ttu-id="32fd8-135">Классификация изображений — это типичная задача Машинного обучения, которая позволяет автоматически классифицировать изображения по нескольким категориям, например:</span><span class="sxs-lookup"><span data-stu-id="32fd8-135">Image Classification is a common Machine Learning task that allows us to automatically classify images into multiple categories such as:</span></span>

* <span data-ttu-id="32fd8-136">для определения того, содержит ли изображение человеческое лицо;</span><span class="sxs-lookup"><span data-stu-id="32fd8-136">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="32fd8-137">для различения изображений котов и собак.</span><span class="sxs-lookup"><span data-stu-id="32fd8-137">Detecting Cats vs. dogs.</span></span>

 <span data-ttu-id="32fd8-138">Или же она помогает определить тип объекта на изображении — еда, игрушка или прибор:</span><span class="sxs-lookup"><span data-stu-id="32fd8-138">Or as in the following images determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="32fd8-139">![Изображение с пиццей](./media/image-classification/220px-Pepperoni_pizza.jpg)
![Изображение с плюшевым мишкой](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![Изображение с тостером](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="32fd8-139">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="32fd8-140">Изображения выше принадлежат Викискладу и имеют следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="32fd8-140">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="32fd8-141">220px-Pepperoni_pizza.jpg, открытый источник, https://commons.wikimedia.org/w/index.php?curid=79505;</span><span class="sxs-lookup"><span data-stu-id="32fd8-141">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="32fd8-142">119px-Nalle_-_a_small_brown_teddy_bear.jpg, автор — [Jonik](https://commons.wikimedia.org/wiki/User:Jonik), автофотография, лицензия CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166;</span><span class="sxs-lookup"><span data-stu-id="32fd8-142">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="32fd8-143">193px-Broodrooster.jpg, автор — [M. Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972), собственное фото, лицензия CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403.</span><span class="sxs-lookup"><span data-stu-id="32fd8-143">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="32fd8-144">При передаче обучения могут использоваться разные стратегии, например *переобучение всех слоев* и *предпоследнего слоя*.</span><span class="sxs-lookup"><span data-stu-id="32fd8-144">Transfer learning includes a few strategies, such as *retrain all layers* and *penultimate layer*.</span></span> <span data-ttu-id="32fd8-145">В этом руководстве поясняется и демонстрируется, как использовать *стратегию предпоследнего слоя*.</span><span class="sxs-lookup"><span data-stu-id="32fd8-145">This tutorial will explain and show how to use the *penultimate layer strategy*.</span></span> <span data-ttu-id="32fd8-146">В рамках *стратегии предпоследнего слоя* повторно используется модель, которая уже предварительно обучена решать конкретную проблему.</span><span class="sxs-lookup"><span data-stu-id="32fd8-146">The *penultimate layer strategy* reuses a model that's already been pre-trained to solve a specific problem.</span></span> <span data-ttu-id="32fd8-147">Последний слой такой модели затем переобучается для решения новой проблемы.</span><span class="sxs-lookup"><span data-stu-id="32fd8-147">The strategy then retrains the final layer of that model to make it solve a new problem.</span></span> <span data-ttu-id="32fd8-148">Повторное использование предварительно обученной модели для работы с новой моделью значительно экономит время и ресурсы.</span><span class="sxs-lookup"><span data-stu-id="32fd8-148">Reusing the pre-trained model as part of your new model will save significant time and resources.</span></span>

<span data-ttu-id="32fd8-149">Ваш пример модели классификации изображений повторно использует [модель Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), популярную модель распознавания изображений, обученную на наборе данных `ImageNet`. В ходе этого процесса модель TensorFlow пытается выполнять классификацию целых изображений по множеству классов, например "Зонтик", "Майка" и "Посудомойка".</span><span class="sxs-lookup"><span data-stu-id="32fd8-149">Your image classification model reuses the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), a popular image recognition model trained on the `ImageNet` dataset where the TensorFlow model tries to classify entire images into a thousand classes, like “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="32fd8-150">`Inception v3 model` можно классифицировать как [сверточную глубокую нейронную сеть](https://en.wikipedia.org/wiki/Convolutional_neural_network), которая может обеспечить достаточную производительность при выполнении сложных задач визуального распознавания, достигая в некоторых областях уровней не ниже или даже выше человеческих возможностей.</span><span class="sxs-lookup"><span data-stu-id="32fd8-150">The `Inception v3 model` can be classified as a [deep convolutional neural network](https://en.wikipedia.org/wiki/Convolutional_neural_network) and can achieve reasonable performance on hard visual recognition tasks, matching or exceeding human performance in some domains.</span></span> <span data-ttu-id="32fd8-151">Эта модель (алгоритм) разработана коллективом исследователей на основе исходной публикации [Rethinking the Inception Architecture for Computer Vision за авторством Szegedy и др.](https://arxiv.org/abs/1512.00567)</span><span class="sxs-lookup"><span data-stu-id="32fd8-151">The model/algorithm was developed by multiple researchers and based on the original paper: ["Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)</span></span>

<span data-ttu-id="32fd8-152">Так как `Inception model` уже обучена на тысячах различных изображений, она содержит [признаки изображений](https://en.wikipedia.org/wiki/Feature_(computer_vision)), необходимые для их идентификации.</span><span class="sxs-lookup"><span data-stu-id="32fd8-152">Because the `Inception model` has already been pre trained on thousands of different images, it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="32fd8-153">Нижние слои признаков изображений распознают простые признаки (например, контуры), а верхние слои — более сложные признаки (например, формы).</span><span class="sxs-lookup"><span data-stu-id="32fd8-153">The lower image feature layers recognize simple features (such as edges) and the higher layers recognize more complex features (such as shapes).</span></span> <span data-ttu-id="32fd8-154">Последний слой обучается на наборе данных намного меньшего размера, так как вы используете уже обученную модель, которая может классифицировать изображения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-154">The final layer is trained against a much smaller set of data because you're starting with a pre trained model that already understands how to classify images.</span></span> <span data-ttu-id="32fd8-155">Так как ваша модель позволяет классифицировать изображения более чем по двум категориям, она относится к [многоклассовым классификаторам](../resources/tasks.md#multiclass-classification).</span><span class="sxs-lookup"><span data-stu-id="32fd8-155">As your model allows you to classify more than two categories, this is an example of a [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span> 

<span data-ttu-id="32fd8-156">`TensorFlow` — это популярный набор средств глубокого (машинного) обучения, который позволяет обучать глубокие нейронные сети и выполнять общие вычисления с числами. Они реализуется в ML.NET как `transformer`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-156">`TensorFlow` is a popular deep learning and machine learning toolkit that enables training deep neural networks (and general numeric computations), and is implemented as a `transformer` in ML.NET.</span></span> <span data-ttu-id="32fd8-157">В этом руководстве он используется для повторного использования `Inception model`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-157">For this tutorial, it's used to reuse the `Inception model`.</span></span>

<span data-ttu-id="32fd8-158">Как показано на схеме ниже, вам нужно добавить ссылки на пакеты NuGet ML.NET в приложения .NET Core или .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="32fd8-158">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="32fd8-159">На внутреннем уровне ML.NET включает и ссылается на встроенную библиотеку `TensorFlow`, которая позволяет создавать код, загружающий существующую обученную модель `TensorFlow` для оценки.</span><span class="sxs-lookup"><span data-stu-id="32fd8-159">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file for scoring.</span></span>  

![Схема преобразования ML.NET с использованием TensorFlow](./media/image-classification/tensorflow-mlnet.png)

<span data-ttu-id="32fd8-161">Модель `Inception model` обучена классифицировать изображения по тысяче категорий, но вам столько категорий не нужно. Также вам нужны четко определенные категории.</span><span class="sxs-lookup"><span data-stu-id="32fd8-161">The `Inception model` is trained to classify images into a thousand categories, but you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="32fd8-162">Перейдем к этапу передачи (`transfer`) этого процесса передачи обучения (`transfer learning`).</span><span class="sxs-lookup"><span data-stu-id="32fd8-162">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="32fd8-163">Вы можете передать способность `Inception model` распознавать и классифицировать изображения в новые ограниченные категории своего классификатора изображений.</span><span class="sxs-lookup"><span data-stu-id="32fd8-163">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>  

 <span data-ttu-id="32fd8-164">Также вы можете переобучить последний слой такой модели с помощью набора из трех категорий:</span><span class="sxs-lookup"><span data-stu-id="32fd8-164">You're going to retrain the final layer of that model using a set of three categories:</span></span>

* <span data-ttu-id="32fd8-165">еда;</span><span class="sxs-lookup"><span data-stu-id="32fd8-165">Food</span></span>
* <span data-ttu-id="32fd8-166">игрушка;</span><span class="sxs-lookup"><span data-stu-id="32fd8-166">Toy</span></span>
* <span data-ttu-id="32fd8-167">прибор.</span><span class="sxs-lookup"><span data-stu-id="32fd8-167">Appliance</span></span>

<span data-ttu-id="32fd8-168">Ваш слой будет использовать [алгоритм мультиномиальной логистической регрессии](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) для поиска корректной категории за минимальное время.</span><span class="sxs-lookup"><span data-stu-id="32fd8-168">Your layer uses a [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) to find the correct category as quickly as possible.</span></span> <span data-ttu-id="32fd8-169">Для поиска ответа этот алгоритм выполняет классификацию на основе вероятностей, присваивая соответствующей категории значение единицы, а всем остальным — нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="32fd8-169">This algorithm classifies using probabilities to determine the answer, giving a one value to the correct category and a zero value to the others.</span></span>  

### <a name="dataset"></a><span data-ttu-id="32fd8-170">DataSet</span><span class="sxs-lookup"><span data-stu-id="32fd8-170">DataSet</span></span>

<span data-ttu-id="32fd8-171">Доступны два источника данных: файл `.tsv` и файлы образов.</span><span class="sxs-lookup"><span data-stu-id="32fd8-171">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="32fd8-172">Файл `tags.tsv` содержит два столбца: первый определен как `ImagePath`, а во втором указана метка `Label`, соответствующая изображению.</span><span class="sxs-lookup"><span data-stu-id="32fd8-172">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="32fd8-173">В примере файла ниже отсутствует строка заголовка. Сам файл выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="32fd8-173">The following example file doesn't have a header row, and looks like this:</span></span>

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

<span data-ttu-id="32fd8-174">Изображения для обучения и тестирования расположены в папках ресурсов, которые вы скачали в виде ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="32fd8-174">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="32fd8-175">Эти изображения принадлежат Викискладу.</span><span class="sxs-lookup"><span data-stu-id="32fd8-175">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="32fd8-176">*[Викисклад](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), бесплатный репозиторий мультимедиа.*</span><span class="sxs-lookup"><span data-stu-id="32fd8-176">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="32fd8-177">Получено в 10:48 17 октября 2018 г. со страниц:</span><span class="sxs-lookup"><span data-stu-id="32fd8-177">Retrieved 10:48, October 17, 2018 from:</span></span>  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a><span data-ttu-id="32fd8-178">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="32fd8-178">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="32fd8-179">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="32fd8-179">Create a project</span></span>

1. <span data-ttu-id="32fd8-180">Создайте **консольное приложение .NET Core** с именем TransferLearningTF.</span><span class="sxs-lookup"><span data-stu-id="32fd8-180">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

2. <span data-ttu-id="32fd8-181">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="32fd8-181">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="32fd8-182">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-182">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="32fd8-183">Выберите nuget.org в качестве источника пакета, откройте вкладку "Обзор" и выполните поиск **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-183">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span> <span data-ttu-id="32fd8-184">Щелкните раскрывающийся список **Версия**, выберите пакет **1.0.0** в списке и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-184">Click on the **Version** drop-down, select the **1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="32fd8-185">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="32fd8-185">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="32fd8-186">Повторите эти шаги для пакетов **Microsoft.ML.ImageAnalytics версии 1.0.0** и **Microsoft.ML.TensorFlow версии 0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-186">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.0.0** and **Microsoft.ML.TensorFlow v0.12.0**.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="32fd8-187">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="32fd8-187">Prepare your data</span></span>

1. <span data-ttu-id="32fd8-188">Скачайте [ZIP-файл каталога с ресурсами проекта](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) и распакуйте его.</span><span class="sxs-lookup"><span data-stu-id="32fd8-188">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

2. <span data-ttu-id="32fd8-189">Скопируйте каталог `assets` в каталог проекта *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="32fd8-189">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="32fd8-190">Этот каталог и его подкаталоги содержат данные и файлы поддержки (за исключением модели Inception, которую вы скачаете и добавите на следующем шаге), необходимые для работы с этим руководством.</span><span class="sxs-lookup"><span data-stu-id="32fd8-190">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

3. <span data-ttu-id="32fd8-191">Скачайте [модель Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) и распакуйте ее.</span><span class="sxs-lookup"><span data-stu-id="32fd8-191">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

4. <span data-ttu-id="32fd8-192">Скопируйте содержание каталога `inception5h`, который вы распаковали, в каталог `assets\inputs-train\inception` проекта *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="32fd8-192">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets\inputs-train\inception` directory.</span></span> <span data-ttu-id="32fd8-193">Этот каталог содержит модель и дополнительные файлы поддержки, необходимые для работы с этим руководством, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="32fd8-193">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Содержание каталога Inception](./media/image-classification/inception-files.png)

5. <span data-ttu-id="32fd8-195">В обозревателе решений щелкните правой кнопкой мыши каждый файл в каталоге и подкаталогах ресурсов и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-195">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="32fd8-196">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-196">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="32fd8-197">Создание классов и определение путей</span><span class="sxs-lookup"><span data-stu-id="32fd8-197">Create classes and define paths</span></span>

<span data-ttu-id="32fd8-198">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="32fd8-198">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

<span data-ttu-id="32fd8-199">Создайте глобальные поля для хранения путей к различным ресурсам, а также глобальные переменные для значений `LabelTokey`, `ImageReal` и `PredictedLabelValue`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-199">Create global fields to hold the paths to the various assets, and global variables for the `LabelTokey`,`ImageReal`, and  `PredictedLabelValue`:</span></span>

* <span data-ttu-id="32fd8-200">`_assetsPath` содержит путь к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="32fd8-200">`_assetsPath` has the path to the assets.</span></span>
* <span data-ttu-id="32fd8-201">`_trainTagsTsv` содержит путь к TSV-файлу с тегами данных изображения обучения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-201">`_trainTagsTsv` has the path to the training image data tags tsv file.</span></span>
* <span data-ttu-id="32fd8-202">`_predictTagsTsv` содержит путь к TSV-файлу с тегами данных изображения прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="32fd8-202">`_predictTagsTsv` has the path to the prediction image data tags tsv file.</span></span>
* <span data-ttu-id="32fd8-203">`_trainImagesFolder` содержит путь к изображениям, используемым для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="32fd8-203">`_trainImagesFolder` has the path to the images used to train the model.</span></span>
* <span data-ttu-id="32fd8-204">`_predictImagesFolder` содержит путь к изображениям, классифицируемым обученной моделью.</span><span class="sxs-lookup"><span data-stu-id="32fd8-204">`_predictImagesFolder` has the path to the images to be classified by the trained model.</span></span>
* <span data-ttu-id="32fd8-205">`_inceptionPb` содержит путь к предварительно обученной модели Inception, которая используется для переобучения вашей модели.</span><span class="sxs-lookup"><span data-stu-id="32fd8-205">`_inceptionPb` has the path to the pre-trained Inception model to be reused to retrain your model.</span></span>
* <span data-ttu-id="32fd8-206">`_inputImageClassifierZip` содержит путь, из которого загружается обученная модель.</span><span class="sxs-lookup"><span data-stu-id="32fd8-206">`_inputImageClassifierZip` has the path where the trained model is loaded from.</span></span>
* <span data-ttu-id="32fd8-207">`_outputImageClassifierZip` содержит путь, по которому сохраняется обученная модель.</span><span class="sxs-lookup"><span data-stu-id="32fd8-207">`_outputImageClassifierZip` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="32fd8-208">`LabelTokey` — это значение `Label`, сопоставленное с ключом.</span><span class="sxs-lookup"><span data-stu-id="32fd8-208">`LabelTokey` is the `Label` value mapped to a key.</span></span>
* <span data-ttu-id="32fd8-209">`ImageReal` — это столбец, содержащий спрогнозированное значение изображения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-209">`ImageReal`  is the column containing the predicted image value.</span></span>
* <span data-ttu-id="32fd8-210">`PredictedLabelValue` — это столбец, содержащий спрогнозированное значение метки.</span><span class="sxs-lookup"><span data-stu-id="32fd8-210">`PredictedLabelValue` is the column containing the predicted label value.</span></span>

<span data-ttu-id="32fd8-211">Добавьте следующий код в строку непосредственно над методом `Main`, чтобы указать эти пути и другие переменные:</span><span class="sxs-lookup"><span data-stu-id="32fd8-211">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="32fd8-212">Создайте несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="32fd8-212">Create some classes for your input data, and predictions.</span></span> <span data-ttu-id="32fd8-213">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="32fd8-213">Add a new class to your project:</span></span>

1. <span data-ttu-id="32fd8-214">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-214">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="32fd8-215">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *ImageData.cs*.</span><span class="sxs-lookup"><span data-stu-id="32fd8-215">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageData.cs*.</span></span> <span data-ttu-id="32fd8-216">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-216">Then, select the **Add** button.</span></span>

    <span data-ttu-id="32fd8-217">Файл *ImageData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="32fd8-217">The *ImageData.cs* file opens in the code editor.</span></span> <span data-ttu-id="32fd8-218">Добавьте следующую инструкцию `using` в начало файла *ImageData.cs*:</span><span class="sxs-lookup"><span data-stu-id="32fd8-218">Add the following `using` statement to the top of *ImageData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

<span data-ttu-id="32fd8-219">Удалите существующее определение класса и добавьте следующий код для класса `ImageData` в файл *ImageData.cs*:</span><span class="sxs-lookup"><span data-stu-id="32fd8-219">Remove the existing class definition and add the following code for the `ImageData` class to the *ImageData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

<span data-ttu-id="32fd8-220">`ImageData` является классом входных данных изображения и имеет следующие поля <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="32fd8-220">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="32fd8-221">`ImagePath` содержит имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-221">`ImagePath` contains the image file name.</span></span>
* <span data-ttu-id="32fd8-222">`Label` содержит значение для метки изображения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-222">`Label` contains a value for the image label.</span></span>

<span data-ttu-id="32fd8-223">Добавьте новый класс в свой проект для `ImagePrediction`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-223">Add a new class to your project for `ImagePrediction`:</span></span>

1. <span data-ttu-id="32fd8-224">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-224">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="32fd8-225">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *ImagePrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="32fd8-225">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImagePrediction.cs*.</span></span> <span data-ttu-id="32fd8-226">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-226">Then, select the **Add** button.</span></span>

    <span data-ttu-id="32fd8-227">Файл *ImagePrediction.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="32fd8-227">The *ImagePrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="32fd8-228">Удалите обе инструкции `using` `System.Collections.Generic` и `System.Text` в начале файла *ImagePrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="32fd8-228">Remove both the `System.Collections.Generic` and the `System.Text` `using` statements at the top of *ImagePrediction.cs*:</span></span>

<span data-ttu-id="32fd8-229">Удалите существующее определение класса и добавьте следующий код с классом `ImagePrediction` в файл *ImagePrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="32fd8-229">Remove the existing class definition and add the following code, which has the `ImagePrediction` class, to the *ImagePrediction.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

<span data-ttu-id="32fd8-230">`ImagePrediction` является классом прогноза изображения и имеет следующие поля:</span><span class="sxs-lookup"><span data-stu-id="32fd8-230">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

* <span data-ttu-id="32fd8-231">`Score` содержит процентное значение достоверности для конкретной классификации изображения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-231">`Score` contains the confidence percentage for a given image classification.</span></span>
* <span data-ttu-id="32fd8-232">`PredictedLabelValue` содержит значение для прогнозируемой метки классификации изображения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-232">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

<span data-ttu-id="32fd8-233">Класс `ImagePrediction` используется для прогнозирования после обучения модели.</span><span class="sxs-lookup"><span data-stu-id="32fd8-233">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="32fd8-234">Он включает `string` (`ImagePath`) с путем к изображению.</span><span class="sxs-lookup"><span data-stu-id="32fd8-234">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="32fd8-235">`Label` используется для применения и переобучения модели.</span><span class="sxs-lookup"><span data-stu-id="32fd8-235">The `Label` is used to reuse and retrain the model.</span></span> <span data-ttu-id="32fd8-236">`PredictedLabelValue` используется для прогнозирования и оценки.</span><span class="sxs-lookup"><span data-stu-id="32fd8-236">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="32fd8-237">Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.</span><span class="sxs-lookup"><span data-stu-id="32fd8-237">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="32fd8-238">[Класс MLContext](xref:Microsoft.ML.MLContext) является отправной точкой для любых операций ML.NET. В результате инициализации класса `mlContext` создается среда ML.NET, которая может использоваться всеми объектами в рамках процесса создания модели.</span><span class="sxs-lookup"><span data-stu-id="32fd8-238">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="32fd8-239">По существу он аналогичен классу `DBContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="32fd8-239">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="32fd8-240">Инициализация переменных в методе Main</span><span class="sxs-lookup"><span data-stu-id="32fd8-240">Initialize variables in Main</span></span>

<span data-ttu-id="32fd8-241">Инициализируйте переменную `mlContext` с использованием нового экземпляра `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-241">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="32fd8-242">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="32fd8-242">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a><span data-ttu-id="32fd8-243">Создание структуры для параметров по умолчанию</span><span class="sxs-lookup"><span data-stu-id="32fd8-243">Create a struct for default parameters</span></span>

<span data-ttu-id="32fd8-244">Модель Inception имеет несколько параметров по умолчанию, которые необходимо передать.</span><span class="sxs-lookup"><span data-stu-id="32fd8-244">The Inception model has several default parameters you need to pass in.</span></span> <span data-ttu-id="32fd8-245">Создайте структуру, чтобы сопоставить значения параметров по умолчанию с понятными именами, с помощью следующего кода сразу после метода `Main()`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-245">Create a struct to map the default parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="32fd8-246">Создание служебного метода для отображения данных</span><span class="sxs-lookup"><span data-stu-id="32fd8-246">Create a display utility method</span></span>

<span data-ttu-id="32fd8-247">Поскольку вы будете отображать данные изображения и связанные прогнозы несколько раз, создайте метод программы отображения для обработки отображения изображений и результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="32fd8-247">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

<span data-ttu-id="32fd8-248">Метод `DisplayResults()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="32fd8-248">The `DisplayResults()` method executes the following tasks:</span></span>

* <span data-ttu-id="32fd8-249">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="32fd8-249">Displays the predicted results.</span></span>

<span data-ttu-id="32fd8-250">Создайте метод `DisplayResults()` сразу после структуры `InceptionSettings` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="32fd8-250">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

<span data-ttu-id="32fd8-251">Метод `Transform()` заполняется `ImagePath` в `ImagePrediction` вместе с прогнозируемыми полями.</span><span class="sxs-lookup"><span data-stu-id="32fd8-251">The `Transform()` method populated `ImagePath` in `ImagePrediction` along with the predicted fields.</span></span> <span data-ttu-id="32fd8-252">В ходе процесса ML.NET каждый компонент добавляет столбцы, что упрощает отображение результатов:</span><span class="sxs-lookup"><span data-stu-id="32fd8-252">As the ML.NET process progresses, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

<span data-ttu-id="32fd8-253">Вы будете вызывать метод `DisplayResults()` в двух методах классификации изображений.</span><span class="sxs-lookup"><span data-stu-id="32fd8-253">You'll call the `DisplayResults()` method in the two image classification methods.</span></span>

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="32fd8-254">Создание служебного метода для TSV-файла</span><span class="sxs-lookup"><span data-stu-id="32fd8-254">Create a .tsv file utility method</span></span>

<span data-ttu-id="32fd8-255">Метод `ReadFromTsv()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="32fd8-255">The `ReadFromTsv()` method executes the following tasks:</span></span>

* <span data-ttu-id="32fd8-256">считывание файла `tags.tsv` с данными изображения;</span><span class="sxs-lookup"><span data-stu-id="32fd8-256">Reads the image data `tags.tsv` file.</span></span>
* <span data-ttu-id="32fd8-257">добавление пути файла к имени файла изображения;</span><span class="sxs-lookup"><span data-stu-id="32fd8-257">Adds the file path to the image file name.</span></span>
* <span data-ttu-id="32fd8-258">загрузка данных файла в объект IEnumerable `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-258">Loads the file data into an IEnumerable`ImageData` object.</span></span>

<span data-ttu-id="32fd8-259">Создайте метод `ReadFromTsv()` сразу после метода `PairAndDisplayResults()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="32fd8-259">Create the `ReadFromTsv()` method, just after the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

<span data-ttu-id="32fd8-260">Указанный ниже код анализирует файл `tags.tsv`, после чего добавляет путь к файлу к имени файла изображения для свойства `ImagePath` и загружает его и `Label` в объект `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-260">The following code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span> <span data-ttu-id="32fd8-261">Добавьте его в качестве первой строки метода `ReadFromTsv()`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-261">Add it as the first line of the `ReadFromTsv()` method.</span></span>  <span data-ttu-id="32fd8-262">Вам понадобится полный путь к файлу для отображения результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="32fd8-262">You need the fully qualified file path to display the prediction results.</span></span>

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
<span data-ttu-id="32fd8-263">В ML.NET есть три основных понятия: [данные](../resources/glossary.md#data), [преобразователи](../resources/glossary.md#transformer) и [средства оценки](../resources/glossary.md#estimator).</span><span class="sxs-lookup"><span data-stu-id="32fd8-263">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

## <a name="reuse-and-tune-pre-trained-model"></a><span data-ttu-id="32fd8-264">Повторное использование и настройка предварительно обученной модели</span><span class="sxs-lookup"><span data-stu-id="32fd8-264">Reuse and tune pre-trained model</span></span>

<span data-ttu-id="32fd8-265">В следующей строке кода в методе `Main()` добавьте приведенный ниже вызов метода `ReuseAndTuneInceptionModel()`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-265">Add the following call to the `ReuseAndTuneInceptionModel()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

<span data-ttu-id="32fd8-266">Метод `ReuseAndTuneInceptionModel()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="32fd8-266">The `ReuseAndTuneInceptionModel()` method executes the following tasks:</span></span>

* <span data-ttu-id="32fd8-267">загрузка данных;</span><span class="sxs-lookup"><span data-stu-id="32fd8-267">Loads the data</span></span>
* <span data-ttu-id="32fd8-268">извлечение и преобразование данных;</span><span class="sxs-lookup"><span data-stu-id="32fd8-268">Extracts and transforms the data.</span></span>
* <span data-ttu-id="32fd8-269">оценка модели TensorFlow;</span><span class="sxs-lookup"><span data-stu-id="32fd8-269">Scores the TensorFlow model.</span></span>
* <span data-ttu-id="32fd8-270">настройка (переобучение) модели;</span><span class="sxs-lookup"><span data-stu-id="32fd8-270">Tunes (retrains) the model.</span></span>
* <span data-ttu-id="32fd8-271">отображение результатов модели;</span><span class="sxs-lookup"><span data-stu-id="32fd8-271">Displays model results.</span></span>
* <span data-ttu-id="32fd8-272">оценка итоговой модели;</span><span class="sxs-lookup"><span data-stu-id="32fd8-272">Evaluates the model.</span></span>
* <span data-ttu-id="32fd8-273">возвращение модели.</span><span class="sxs-lookup"><span data-stu-id="32fd8-273">Returns the model.</span></span>

<span data-ttu-id="32fd8-274">Создайте метод `ReuseAndTuneInceptionModel()` сразу после структуры `InceptionSettings` и непосредственно перед методом `DisplayResults()` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="32fd8-274">Create the `ReuseAndTuneInceptionModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a><span data-ttu-id="32fd8-275">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="32fd8-275">Load the data</span></span>

<span data-ttu-id="32fd8-276">Данные в ML.NET представлены [классом IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="32fd8-276">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="32fd8-277">`IDataView` позволяет гибко и полно описывать табличные данные (числовые и текстовые).</span><span class="sxs-lookup"><span data-stu-id="32fd8-277">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="32fd8-278">Данные можно загружать в объект `IDataView` из текстового файла или в режиме реального времени (например, из базы данных SQL или файлов журнала).</span><span class="sxs-lookup"><span data-stu-id="32fd8-278">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="32fd8-279">Загрузите данные с помощью оболочки `MLContext.Data.LoadFromTextFile`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-279">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="32fd8-280">Добавьте в следующую строку метода `ReuseAndTuneInceptionModel()` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="32fd8-280">Add the following code as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="32fd8-281">Извлечение компонентов и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="32fd8-281">Extract Features and transform the data</span></span>

<span data-ttu-id="32fd8-282">Предварительная обработка и очистка данных — это очень важные задачи, которые нужно выполнить перед использованием набора данных для машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-282">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span>  <span data-ttu-id="32fd8-283">Использование данных напрямую без этих задач моделирования может дать неправильные результаты.</span><span class="sxs-lookup"><span data-stu-id="32fd8-283">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="32fd8-284">Алгоритмы машинного обучения распознают данные с [присвоенными признаками](../resources/glossary.md#feature), поэтому при работе с глубокими нейронными сетями вам необходимо преобразовать изображения в подходящий для сети формат.</span><span class="sxs-lookup"><span data-stu-id="32fd8-284">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, and when dealing with deep neural networks you must adapt the images to the format expected by the network.</span></span> <span data-ttu-id="32fd8-285">Этот формат — [числовой вектор](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="32fd8-285">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="32fd8-286">После обучения и оценки создайте прогноз с помощью значений столбца **Label**.</span><span class="sxs-lookup"><span data-stu-id="32fd8-286">After training and evaluation, predict with the **Label** column values.</span></span> <span data-ttu-id="32fd8-287">Так как вы используете предварительно обученную модель, сопоставьте поля с новой моделью с помощью метода [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A).</span><span class="sxs-lookup"><span data-stu-id="32fd8-287">As you're using a pre-trained model, map fields to the new model with the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method.</span></span> <span data-ttu-id="32fd8-288">Этот метод преобразует `Label` в столбец с числовыми ключами (`LabelTokey`) и добавляет его в виде нового столбца набора данных.  Присвойте этому средству оценки `estimator` имя, так как вы также добавите к нему метод обучения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-288">This method transforms the `Label` into a numeric key type (`LabelTokey`) column and add it as new dataset column:  Name this `estimator` as you'll also add the trainer to it.</span></span> <span data-ttu-id="32fd8-289">Добавьте следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="32fd8-289">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

<span data-ttu-id="32fd8-290">Ваше средство оценки обработки изображений использует средства присвоения признаков предварительно обученной [глубокой нейронной сети (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) для выделения признаков.</span><span class="sxs-lookup"><span data-stu-id="32fd8-290">Your image processing estimator uses pre-trained [Deep Neural Network(DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizers for feature extraction.</span></span> <span data-ttu-id="32fd8-291">При работе с глубокими нейронными сетями вам необходимо преобразовать изображения в подходящий для сети формат.</span><span class="sxs-lookup"><span data-stu-id="32fd8-291">When dealing with deep neural networks, you  adapt the images to the expected network format.</span></span> <span data-ttu-id="32fd8-292">По этой причине вам нужно использовать несколько преобразований изображений, чтобы вы могли предоставить модели данные изображений в подходящем формате:</span><span class="sxs-lookup"><span data-stu-id="32fd8-292">This is the reason you use several image transforms to get the image data into the model's expected form:</span></span>

1. <span data-ttu-id="32fd8-293">Изображения преобразования `LoadImages` загружаются в память как растровые изображения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-293">The `LoadImages`transform images are loaded in memory as a Bitmap type.</span></span>
2. <span data-ttu-id="32fd8-294">Преобразование `ResizeImages` изменяет размер изображений, так как предварительно обученная модель имеет определенные значения ширины и высоты изображений.</span><span class="sxs-lookup"><span data-stu-id="32fd8-294">The `ResizeImages` transform resizes the images as the pre-trained model has a defined input image width and height.</span></span>
3. <span data-ttu-id="32fd8-295">Преобразование `ExtractPixels` извлекает пиксели из входных изображений и преобразует их в числовой вектор.</span><span class="sxs-lookup"><span data-stu-id="32fd8-295">The `ExtractPixels` transform extracts the pixels from the input images and converts them into a numeric vector.</span></span>

<span data-ttu-id="32fd8-296">Добавьте эти преобразования изображений в следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="32fd8-296">Add these image transforms as the next lines of code:</span></span>

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

<span data-ttu-id="32fd8-297">`LoadTensorFlowModel` является удобным методом, который позволяет загружать модель `TensorFlow` один раз, а затем создает `TensorFlowEstimator` с помощью `ScoreTensorFlowModel`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-297">The `LoadTensorFlowModel` is a convenience method that allows the `TensorFlow` model to be loaded once and then creates the `TensorFlowEstimator` using `ScoreTensorFlowModel`.</span></span> <span data-ttu-id="32fd8-298">Компонент `ScoreTensorFlowModel` выделяет указанные выходные данные (признаки изображения `Inception model``softmax2_pre_activation`) и присваивает набору данных оценку с помощью предварительно обученной модели `TensorFlow`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-298">The `ScoreTensorFlowModel` extracts specified outputs (the `Inception model`'s image features `softmax2_pre_activation`), and scores a dataset using the pre-trained `TensorFlow` model.</span></span>

<span data-ttu-id="32fd8-299">Узел `softmax2_pre_activation` обеспечивает поддержку модели, определяя классы изображений.</span><span class="sxs-lookup"><span data-stu-id="32fd8-299">`softmax2_pre_activation` assists the model with determining which class the images belongs to.</span></span> <span data-ttu-id="32fd8-300">Узел `softmax2_pre_activation` возвращает значение вероятности для каждой категории изображения, причем сумма всех таких вероятностей должна равняться 1.</span><span class="sxs-lookup"><span data-stu-id="32fd8-300">`softmax2_pre_activation` returns a probability for each of the categories for an image, and all of those probabilities must add up to 1.</span></span> <span data-ttu-id="32fd8-301">Предполагается, что изображение принадлежит только к одной категории, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="32fd8-301">It assumes that an image will belong to only one category, as shown in the following example:</span></span>

| <span data-ttu-id="32fd8-302">Класс</span><span class="sxs-lookup"><span data-stu-id="32fd8-302">Class</span></span>         | <span data-ttu-id="32fd8-303">Вероятность</span><span class="sxs-lookup"><span data-stu-id="32fd8-303">Probability</span></span>   |
| ------------- | ------------- |
| `Food`        |  <span data-ttu-id="32fd8-304">0,001</span><span class="sxs-lookup"><span data-stu-id="32fd8-304">0.001</span></span>        |
| `Toy`         |  <span data-ttu-id="32fd8-305">0,95</span><span class="sxs-lookup"><span data-stu-id="32fd8-305">0.95</span></span>         |
| `Appliance`   |  <span data-ttu-id="32fd8-306">0,06</span><span class="sxs-lookup"><span data-stu-id="32fd8-306">0.06</span></span>         |

<span data-ttu-id="32fd8-307">Добавьте `TensorFlowTransform` к `estimator` с помощью такой строки кода:</span><span class="sxs-lookup"><span data-stu-id="32fd8-307">Append the `TensorFlowTransform` to the `estimator` with the following line of code:</span></span>

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a><span data-ttu-id="32fd8-308">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="32fd8-308">Choose a training algorithm</span></span>

<span data-ttu-id="32fd8-309">Чтобы добавить алгоритм обучения, вызовите метод оболочки `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-309">To add the training algorithm, call the `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` wrapper method.</span></span>  <span data-ttu-id="32fd8-310">Класс [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) добавляется в `estimator` и принимает признаки изображения Inception (`softmax2_pre_activation`) и входные параметры `Label` для обучения на основе исторических данных.</span><span class="sxs-lookup"><span data-stu-id="32fd8-310">The [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) is appended to the `estimator` and accepts the Inception image features (`softmax2_pre_activation`) and the `Label` input parameters to learn from the historic data.</span></span>  <span data-ttu-id="32fd8-311">Добавьте метод обучения с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="32fd8-311">Add the trainer with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

<span data-ttu-id="32fd8-312">Вам также нужно сопоставить `predictedlabel` с `predictedlabelvalue`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-312">You also need to map the `predictedlabel` to the `predictedlabelvalue`:</span></span>

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

<span data-ttu-id="32fd8-313">Метод `Fit()` обучает модель путем преобразования набора данных и применения обучения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-313">The `Fit()` method trains your model by transforming the dataset and applying the training.</span></span> <span data-ttu-id="32fd8-314">Обучите модель на основе обучающего набора данных и получите обученную модель, добавив в метод `ReuseAndTuneInceptionModel()` следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="32fd8-314">Fit the model to the training dataset and return the trained model by adding the following as the next line of code in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

<span data-ttu-id="32fd8-315">Метод [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) делает прогнозы для нескольких входных строк тестового набора данных.</span><span class="sxs-lookup"><span data-stu-id="32fd8-315">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>  <span data-ttu-id="32fd8-316">Преобразуйте данные `Training`, добавив в метод `ReuseAndTuneInceptionModel()` следующий код:</span><span class="sxs-lookup"><span data-stu-id="32fd8-316">Transform the `Training` data by adding the following code to `ReuseAndTuneInceptionModel()`:</span></span>

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

<span data-ttu-id="32fd8-317">Преобразуйте представления `DataViews` данных изображений и прогнозов в строго типизированные объекты `IEnumerables`, чтобы связать их для более удобного отображения.</span><span class="sxs-lookup"><span data-stu-id="32fd8-317">Convert your image data and prediction `DataViews` into strongly-typed `IEnumerables` to pair for easier display.</span></span> <span data-ttu-id="32fd8-318">Для этого воспользуйтесь методом `MLContext.CreateEnumerable()`, добавив следующий код:</span><span class="sxs-lookup"><span data-stu-id="32fd8-318">Use the `MLContext.CreateEnumerable()` method to do that, using the following code:</span></span>

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

<span data-ttu-id="32fd8-319">Вызовите метод `DisplayResults()`, чтобы отобразить данные и прогнозы, добавив в метод `ReuseAndTuneInceptionModel()` следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="32fd8-319">Call the `DisplayResults()` method to display your data and predictions as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

<span data-ttu-id="32fd8-320">Получив прогноз, с помощью метода [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) вы сможете:</span><span class="sxs-lookup"><span data-stu-id="32fd8-320">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

* <span data-ttu-id="32fd8-321">оценить модель (сравнивает спрогнозированные значения с фактическим набором данных `Labels`);</span><span class="sxs-lookup"><span data-stu-id="32fd8-321">Assesses the model (compares the predicted values with the actual dataset `Labels`).</span></span>

* <span data-ttu-id="32fd8-322">получить метрики производительности модели.</span><span class="sxs-lookup"><span data-stu-id="32fd8-322">Returns the model performance metrics.</span></span>

<span data-ttu-id="32fd8-323">В качестве следующей строки в методе `ReuseAndTuneInceptionModel()` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="32fd8-323">Add the following code to the `ReuseAndTuneInceptionModel()` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

<span data-ttu-id="32fd8-324">Для классификации изображений выполняется оценка следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="32fd8-324">The following metrics are evaluated for image classification:</span></span>

* <span data-ttu-id="32fd8-325">`Log-loss` — см. раздел [Логарифмические потери](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="32fd8-325">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="32fd8-326">Значение логарифмических потерь должно быть максимально близко к нулю.</span><span class="sxs-lookup"><span data-stu-id="32fd8-326">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="32fd8-327">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-327">`Per class Log-loss`.</span></span> <span data-ttu-id="32fd8-328">Значение логарифмических потерь для каждого класса должно быть максимально близко к нулю.</span><span class="sxs-lookup"><span data-stu-id="32fd8-328">You want per class Log-loss to be as close to zero as possible.</span></span>

<span data-ttu-id="32fd8-329">Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:</span><span class="sxs-lookup"><span data-stu-id="32fd8-329">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 <span data-ttu-id="32fd8-330">Добавьте следующий код, чтобы возвращать обученную модель:</span><span class="sxs-lookup"><span data-stu-id="32fd8-330">Add the following code to return the trained model as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a><span data-ttu-id="32fd8-331">классифицировать изображения с помощью загруженной модели.</span><span class="sxs-lookup"><span data-stu-id="32fd8-331">Classify images with a loaded model</span></span>

<span data-ttu-id="32fd8-332">Добавьте такой вызов в метод `ClassifyImages()` в следующей строке кода в методе `Main`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-332">Add the following call to the `ClassifyImages()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

<span data-ttu-id="32fd8-333">Метод `ClassifyImages()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="32fd8-333">The `ClassifyImages()` method executes the following tasks:</span></span>

* <span data-ttu-id="32fd8-334">считывание TSV-файла в интерфейс `IEnumerable`;</span><span class="sxs-lookup"><span data-stu-id="32fd8-334">Reads .TSV file into `IEnumerable`.</span></span>
* <span data-ttu-id="32fd8-335">создание прогноза для классификаций изображений на основе проверочных данных.</span><span class="sxs-lookup"><span data-stu-id="32fd8-335">Predicts image classifications based on test data.</span></span>

<span data-ttu-id="32fd8-336">Создайте метод `ClassifyImages()` сразу после метода `ReuseAndTuneInceptionModel()` и непосредственно перед методом `PairAndDisplayResults()` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="32fd8-336">Create the `ClassifyImages()` method, just after the `ReuseAndTuneInceptionModel()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="32fd8-337">Сначала вызовите метод `ReadFromTsv()` для создания класса `IEnumerable<ImageData>`, который содержит полный путь для каждого значения `ImagePath`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-337">First, call the `ReadFromTsv()` method to create an `IEnumerable<ImageData>` class that contains the fully qualified path for each `ImagePath`.</span></span> <span data-ttu-id="32fd8-338">Вам потребуется такой путь к файлу для связывания данных и результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="32fd8-338">You need that file path to pair your data and prediction results.</span></span> <span data-ttu-id="32fd8-339">Вам также нужно преобразовать класс `IEnumerable<ImageData>` в класс `IDataView`, который будет использоваться для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="32fd8-339">You also need to convert the `IEnumerable<ImageData>` class to an `IDataView` that you will use to predict.</span></span> <span data-ttu-id="32fd8-340">Добавьте такой код в следующие две строки в методе `ClassifyImages()`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-340">Add the following code as the next two lines in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

<span data-ttu-id="32fd8-341">Как вы это уже сделали с данными изображения для обучения, создайте прогноз категории для проверочных данных изображения с помощью метода [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) переданной модели.</span><span class="sxs-lookup"><span data-stu-id="32fd8-341">As you did previously with the training image data, predict the category of the test image data using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the model passed in.</span></span> <span data-ttu-id="32fd8-342">Добавьте следующий код в метод `ClassifyImages()`, чтобы создавать прогнозы и преобразовывать `predictions` `IDataView` в `IEnumerable` для связывания и отображения:</span><span class="sxs-lookup"><span data-stu-id="32fd8-342">Add the following code to the `ClassifyImages()` method for the predictions and to convert the `predictions` `IDataView` into an `IEnumerable` for pairing and display:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

<span data-ttu-id="32fd8-343">Чтобы связать и отобразить проверочные данные изображения и прогнозы, добавьте такой код для вызова ранее созданного метода `DisplayResults()` в следующую строку метода `ClassifyImages()`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-343">To pair and display your test image data and predictions, add the following code to call the `DisplayResults()` method previously created as the next line in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a><span data-ttu-id="32fd8-344">Классификация отдельного изображения с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="32fd8-344">Classify a single image with a loaded model</span></span>

<span data-ttu-id="32fd8-345">Добавьте такой вызов в метод `ClassifySingleImage()` в следующей строке кода в методе `Main`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-345">Add the following call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

<span data-ttu-id="32fd8-346">Метод `ClassifySingleImage()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="32fd8-346">The `ClassifySingleImage()` method executes the following tasks:</span></span>

* <span data-ttu-id="32fd8-347">загрузка экземпляра `ImageData`;</span><span class="sxs-lookup"><span data-stu-id="32fd8-347">Loads an `ImageData` instance.</span></span>
* <span data-ttu-id="32fd8-348">создание прогноза для классификации изображений на основе проверочных данных.</span><span class="sxs-lookup"><span data-stu-id="32fd8-348">Predicts image classification based on test data.</span></span>

<span data-ttu-id="32fd8-349">Создайте метод `ClassifySingleImage()` сразу после метода `ClassifyImages()` и непосредственно перед методом `PairAndDisplayResults()` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="32fd8-349">Create the `ClassifySingleImage()` method, just after the `ClassifyImages()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="32fd8-350">Сначала создайте класс `ImageData`, который хранит полный путь и имя файла изображения для одного значения `ImagePath`.</span><span class="sxs-lookup"><span data-stu-id="32fd8-350">First, create an `ImageData` class that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="32fd8-351">Добавьте такой код в следующие строки в методе `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-351">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

<span data-ttu-id="32fd8-352">Класс [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) — это удобный API, который создает прогноз на основе одного экземпляра данных.</span><span class="sxs-lookup"><span data-stu-id="32fd8-352">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API that performs a prediction on a single instance of data.</span></span> <span data-ttu-id="32fd8-353">Функция [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) создает прогноз по одному столбцу данных.</span><span class="sxs-lookup"><span data-stu-id="32fd8-353">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span> <span data-ttu-id="32fd8-354">Передайте значение `imageData` классу `PredictionEngine`, чтобы спрогнозировать категорию изображения, добавив следующий код в `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-354">Pass `imageData` to the `PredictionEngine` to predict the image category by adding the following code to `ClassifySingleImage()`:</span></span>

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

<span data-ttu-id="32fd8-355">Отобразите результат прогнозирования с помощью следующей строки кода в методе `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="32fd8-355">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a><span data-ttu-id="32fd8-356">Результаты</span><span class="sxs-lookup"><span data-stu-id="32fd8-356">Results</span></span>

<span data-ttu-id="32fd8-357">Выполнив предыдущие шаги, запустите консольное приложение (CTRL+F5).</span><span class="sxs-lookup"><span data-stu-id="32fd8-357">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="32fd8-358">Результаты выполнения должны выглядеть примерно так, как указано ниже.</span><span class="sxs-lookup"><span data-stu-id="32fd8-358">Your results should be similar to the following output.</span></span>  <span data-ttu-id="32fd8-359">Кроме того, могут выводиться предупреждения или сообщения об обработке, но для удобства здесь мы убрали их.</span><span class="sxs-lookup"><span data-stu-id="32fd8-359">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training classification model ===============
Image: broccoli.jpg predicted as: food with score: 0.976743
Image: pizza.jpg predicted as: food with score: 0.9751652
Image: pizza2.jpg predicted as: food with score: 0.9660203
Image: teddy2.jpg predicted as: toy with score: 0.9748783
Image: teddy3.jpg predicted as: toy with score: 0.9829691
Image: teddy4.jpg predicted as: toy with score: 0.9868168
Image: toaster.jpg predicted as: appliance with score: 0.9769174
Image: toaster2.png predicted as: appliance with score: 0.9800823
=============== Classification metrics ===============
LogLoss is: 0.0228266745633507
PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="32fd8-360">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="32fd8-360">Congratulations!</span></span> <span data-ttu-id="32fd8-361">Вы успешно создали модель машинного обучения для классификации изображений на основе предварительно обученной модели `TensorFlow` в ML.NET.</span><span class="sxs-lookup"><span data-stu-id="32fd8-361">You've now successfully built a machine learning model for image classification by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="32fd8-362">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="32fd8-362">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="32fd8-363">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="32fd8-363">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="32fd8-364">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="32fd8-364">Understand the problem</span></span>
> * <span data-ttu-id="32fd8-365">повторно использовать и настраивать предварительно обученную модель;</span><span class="sxs-lookup"><span data-stu-id="32fd8-365">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="32fd8-366">классифицировать изображения с помощью загруженной модели.</span><span class="sxs-lookup"><span data-stu-id="32fd8-366">Classify images with a loaded model</span></span>

<span data-ttu-id="32fd8-367">Ознакомьтесь с примерами Машинного обучения в репозитории GitHub, чтобы подробнее изучить расширенный пример классификации изображений.</span><span class="sxs-lookup"><span data-stu-id="32fd8-367">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="32fd8-368">Репозиторий GitHub dotnet/machinelearning-samples</span><span class="sxs-lookup"><span data-stu-id="32fd8-368">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
