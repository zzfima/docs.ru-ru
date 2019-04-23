---
title: Создание специализированного классификатора ML.NET с помощью TensorFlow
description: Узнайте, как создать пользовательский классификатор изображений ML.NET в сценарии передачи обучения TensorFlow для классификации изображений путем повторного использования предварительно обученной модели TensorFlow.
ms.date: 04/05/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9b9ac1f1f15b4003a19a3d30d6cadf3e86946376
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517971"
---
# <a name="tutorial-build-an-mlnet-custom-image-classifier-with-tensorflow"></a><span data-ttu-id="274a5-103">Учебник. Создание специализированного классификатора ML.NET с помощью TensorFlow</span><span class="sxs-lookup"><span data-stu-id="274a5-103">Tutorial: Build an ML.NET custom image classifier with TensorFlow</span></span>

<span data-ttu-id="274a5-104">В этом руководстве показано, как вы можете использовать обученную модель `TensorFlow` классификатора изображений, чтобы создать пользовательскую модель для классификации изображений по нескольким категориям.</span><span class="sxs-lookup"><span data-stu-id="274a5-104">This sample tutorial illustrates how you can use an already trained Image Classifier `TensorFlow` model to build a new custom model to classify images into a few categories.</span></span>

<span data-ttu-id="274a5-105">Хотели ли бы вы иметь возможность повторно использовать предварительно обученную модель для решения похожей проблемы, а также переобучать для этой цели все или некоторые слои такой модели?</span><span class="sxs-lookup"><span data-stu-id="274a5-105">What if you could reuse a model that's already been pre trained to solve a similar problem and retrain either all or some of the layers of that model to make it solve your problem?</span></span> <span data-ttu-id="274a5-106">Подход с повторным использованием части уже обученной модели для создания новой называется [передачей обучения](https://en.wikipedia.org/wiki/Transfer_learning).</span><span class="sxs-lookup"><span data-stu-id="274a5-106">This technique of reusing part of an already trained model to build a new model is known as [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning).</span></span>

<span data-ttu-id="274a5-107">Обучение модели для [классификации изображений](https://en.wikipedia.org/wiki/Outline_of_object_recognition) с нуля предусматривает настройку нескольких миллионов параметров, а также использование огромных объемов помеченных данных обучения и вычислительных ресурсов (сотни часов работы GPU).</span><span class="sxs-lookup"><span data-stu-id="274a5-107">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="274a5-108">Хотя передача обучения не настолько эффективна, как обучение пользовательской модели с нуля, этот подход позволяет значительно ускорить соответствующий процесс с использованием всего нескольких тысяч изображений (а не миллионов помеченных изображений) для быстрого создания пользовательской модели (в пределах часа на компьютере без GPU).</span><span class="sxs-lookup"><span data-stu-id="274a5-108">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span>

<span data-ttu-id="274a5-109">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="274a5-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="274a5-110">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="274a5-110">Understand the problem</span></span>
> * <span data-ttu-id="274a5-111">повторно использовать и настраивать предварительно обученную модель;</span><span class="sxs-lookup"><span data-stu-id="274a5-111">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="274a5-112">классифицировать изображения.</span><span class="sxs-lookup"><span data-stu-id="274a5-112">Classify Images</span></span>

> [!NOTE]
> <span data-ttu-id="274a5-113">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="274a5-113">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="274a5-114">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="274a5-114">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="274a5-115">Сейчас в этом руководстве и соответствующем примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="274a5-115">This tutorial and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="274a5-116">Подробнее. см. в репозитории GitHub [dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="274a5-116">For more information, see the release notes at the [dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes) GitHub repository.</span></span>

## <a name="image-classification-sample-overview"></a><span data-ttu-id="274a5-117">Пример классификации изображений</span><span class="sxs-lookup"><span data-stu-id="274a5-117">Image classification sample overview</span></span>

<span data-ttu-id="274a5-118">Этот пример представляет собой консольное приложение, которое использует ML.NET для создания классификатора изображений путем повторного применения предварительно обученной модели для классификации изображений на основе небольшого объема данных обучения.</span><span class="sxs-lookup"><span data-stu-id="274a5-118">The sample is a console application that uses ML.NET to build an image classifier by reusing a pre-trained model to classify images with a small amount of training data.</span></span>

<span data-ttu-id="274a5-119">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="274a5-119">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="274a5-120">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="274a5-120">Prerequisites</span></span>

* <span data-ttu-id="274a5-121">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="274a5-121">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="274a5-122">Пакет Nuget для Microsoft.ML 0.10.0.</span><span class="sxs-lookup"><span data-stu-id="274a5-122">Microsoft.ML 0.10.0 Nuget package</span></span>
* <span data-ttu-id="274a5-123">Пакет Nuget для Microsoft.ML.ImageAnalytics 0.10.0.</span><span class="sxs-lookup"><span data-stu-id="274a5-123">Microsoft.ML.ImageAnalytics 0.10.0 Nuget package</span></span>
* <span data-ttu-id="274a5-124">Пакет Nuget для Microsoft.ML.TensorFlow 0.10.0.</span><span class="sxs-lookup"><span data-stu-id="274a5-124">Microsoft.ML.TensorFlow 0.10.0 Nuget package</span></span>

* [<span data-ttu-id="274a5-125">ZIP-файл каталога ресурсов руководства.</span><span class="sxs-lookup"><span data-stu-id="274a5-125">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="274a5-126">Модель машинного обучения Inception версии 3.</span><span class="sxs-lookup"><span data-stu-id="274a5-126">The InceptionV3 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="274a5-127">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="274a5-127">Select the appropriate machine learning task</span></span>

<span data-ttu-id="274a5-128">[Глубокое обучение](https://en.wikipedia.org/wiki/Deep_learning) — это разновидность машинного обучения, которая произвела революцию в области компьютерного зрения и распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="274a5-128">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="274a5-129">Модели глубокого обучения обучаются на крупных наборах [помеченных данных](https://en.wikipedia.org/wiki/Labeled_data) с использованием [нейронных сетей](https://en.wikipedia.org/wiki/Artificial_neural_network), которые содержат множество слоев обучения.</span><span class="sxs-lookup"><span data-stu-id="274a5-129">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="274a5-130">Глубокое обучение:</span><span class="sxs-lookup"><span data-stu-id="274a5-130">Deep learning:</span></span>

* <span data-ttu-id="274a5-131">лучше выполняет некоторые задачи, например в области компьютерного зрения;</span><span class="sxs-lookup"><span data-stu-id="274a5-131">Performs better on some tasks like Computer Vision.</span></span>

* <span data-ttu-id="274a5-132">хорошо работает с огромными объемами данных.</span><span class="sxs-lookup"><span data-stu-id="274a5-132">Performs well on huge data amounts.</span></span>

<span data-ttu-id="274a5-133">Классификация изображений — это типичная задача Машинного обучения, которая позволяет автоматически классифицировать изображения по нескольким категориям, например:</span><span class="sxs-lookup"><span data-stu-id="274a5-133">Image Classification is a common Machine Learning task that allows us to automatically classify images into multiple categories such as:</span></span>

* <span data-ttu-id="274a5-134">для определения того, содержит ли изображение человеческое лицо;</span><span class="sxs-lookup"><span data-stu-id="274a5-134">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="274a5-135">для различения изображений котов и собак.</span><span class="sxs-lookup"><span data-stu-id="274a5-135">Detecting Cats vs. dogs.</span></span>

 <span data-ttu-id="274a5-136">Или же она помогает определить тип объекта на изображении — еда, игрушка или прибор:</span><span class="sxs-lookup"><span data-stu-id="274a5-136">Or as in the following images determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="274a5-137">![Изображение с пиццей](./media/image-classification/220px-Pepperoni_pizza.jpg)
![Изображение с плюшевым мишкой](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![Изображение с тостером](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="274a5-137">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="274a5-138">Изображения выше принадлежат Викискладу и имеют следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="274a5-138">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="274a5-139">220px-Pepperoni_pizza.jpg, открытый источник, https://commons.wikimedia.org/w/index.php?curid=79505;</span><span class="sxs-lookup"><span data-stu-id="274a5-139">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="274a5-140">119px-Nalle_-_a_small_brown_teddy_bear.jpg, автор — [Jonik](https://commons.wikimedia.org/wiki/User:Jonik), автофотография, лицензия CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166;</span><span class="sxs-lookup"><span data-stu-id="274a5-140">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="274a5-141">193px-Broodrooster.jpg, автор — [M. Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972), собственное фото, лицензия CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403.</span><span class="sxs-lookup"><span data-stu-id="274a5-141">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="274a5-142">При передаче обучения могут использоваться разные стратегии, например *переобучение всех слоев* и *предпоследнего слоя*.</span><span class="sxs-lookup"><span data-stu-id="274a5-142">Transfer learning includes a few strategies, such as *retrain all layers* and *penultimate layer*.</span></span> <span data-ttu-id="274a5-143">В этом руководстве поясняется и демонстрируется, как использовать *стратегию предпоследнего слоя*.</span><span class="sxs-lookup"><span data-stu-id="274a5-143">This tutorial will explain and show how to use the *penultimate layer strategy*.</span></span> <span data-ttu-id="274a5-144">В рамках *стратегии предпоследнего слоя* повторно используется модель, которая уже предварительно обучена решать конкретную проблему.</span><span class="sxs-lookup"><span data-stu-id="274a5-144">The *penultimate layer strategy* reuses a model that's already been pre-trained to solve a specific problem.</span></span> <span data-ttu-id="274a5-145">Последний слой такой модели затем переобучается для решения новой проблемы.</span><span class="sxs-lookup"><span data-stu-id="274a5-145">The strategy then retrains the final layer of that model to make it solve a new problem.</span></span> <span data-ttu-id="274a5-146">Повторное использование предварительно обученной модели для работы с новой моделью значительно экономит время и ресурсы.</span><span class="sxs-lookup"><span data-stu-id="274a5-146">Reusing the pre-trained model as part of your new model will save significant time and resources.</span></span>

<span data-ttu-id="274a5-147">Ваш пример модели классификации изображений повторно использует [модель Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), популярную модель распознавания изображений, обученную на наборе данных `ImageNet`. В ходе этого процесса модель TensorFlow пытается выполнять классификацию целых изображений по множеству классов, например "Зонтик", "Майка" и "Посудомойка".</span><span class="sxs-lookup"><span data-stu-id="274a5-147">Your image classification model reuses the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), a popular image recognition model trained on the `ImageNet` dataset where the TensorFlow model tries to classify entire images into a thousand classes, like “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="274a5-148">`Inception v3 model` можно классифицировать как [сверточную глубокую нейронную сеть](https://en.wikipedia.org/wiki/Convolutional_neural_network), которая может обеспечить достаточную производительность при выполнении сложных задач визуального распознавания, достигая в некоторых областях уровней не ниже или даже выше человеческих возможностей.</span><span class="sxs-lookup"><span data-stu-id="274a5-148">The `Inception v3 model` can be classified as a [deep convolutional neural network](https://en.wikipedia.org/wiki/Convolutional_neural_network) and can achieve reasonable performance on hard visual recognition tasks, matching or exceeding human performance in some domains.</span></span> <span data-ttu-id="274a5-149">Эта модель (алгоритм) разработана коллективом исследователей на основе исходной публикации [Rethinking the Inception Architecture for Computer Vision за авторством Szegedy и др.](https://arxiv.org/abs/1512.00567)</span><span class="sxs-lookup"><span data-stu-id="274a5-149">The model/algorithm was developed by multiple researchers and based on the original paper: ["Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)</span></span>

<span data-ttu-id="274a5-150">Так как `Inception model` уже обучена на тысячах различных изображений, она содержит [признаки изображений](https://en.wikipedia.org/wiki/Feature_(computer_vision)), необходимые для их идентификации.</span><span class="sxs-lookup"><span data-stu-id="274a5-150">Because the `Inception model` has already been pre trained on thousands of different images, it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="274a5-151">Нижние слои признаков изображений распознают простые признаки (например, контуры), а верхние слои — более сложные признаки (например, формы).</span><span class="sxs-lookup"><span data-stu-id="274a5-151">The lower image feature layers recognize simple features (such as edges) and the higher layers recognize more complex features (such as shapes).</span></span> <span data-ttu-id="274a5-152">Последний слой обучается на наборе данных намного меньшего размера, так как вы используете уже обученную модель, которая может классифицировать изображения.</span><span class="sxs-lookup"><span data-stu-id="274a5-152">The final layer is trained against a much smaller set of data because you're starting with a pre trained model that already understands how to classify images.</span></span> <span data-ttu-id="274a5-153">Так как ваша модель позволяет классифицировать изображения более чем по двум категориям, она относится к [многоклассовым классификаторам](../resources/tasks.md#multiclass-classification).</span><span class="sxs-lookup"><span data-stu-id="274a5-153">As your model allows you to classify more than two categories, this is an example of a [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span> 

<span data-ttu-id="274a5-154">`TensorFlow` — это популярный набор средств глубокого (машинного) обучения, который позволяет обучать глубокие нейронные сети и выполнять общие вычисления с числами. Они реализуется в ML.NET как `transformer`.</span><span class="sxs-lookup"><span data-stu-id="274a5-154">`TensorFlow` is a popular deep learning and machine learning toolkit that enables training deep neural networks (and general numeric computations), and is implemented as a `transformer` in ML.NET.</span></span> <span data-ttu-id="274a5-155">В этом руководстве он используется для повторного использования `Inception model`.</span><span class="sxs-lookup"><span data-stu-id="274a5-155">For this tutorial, it's used to reuse the `Inception model`.</span></span>

<span data-ttu-id="274a5-156">Как показано на схеме ниже, вам нужно добавить ссылки на пакеты NuGet ML.NET в приложения .NET Core или .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="274a5-156">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="274a5-157">На внутреннем уровне ML.NET включает и ссылается на встроенную библиотеку `TensorFlow`, которая позволяет создавать код, загружающий существующую обученную модель `TensorFlow` для оценки.</span><span class="sxs-lookup"><span data-stu-id="274a5-157">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file for scoring.</span></span>  

![Схема преобразования ML.NET с использованием TensorFlow](./media/image-classification/tensorflow-mlnet.png)

<span data-ttu-id="274a5-159">Модель `Inception model` обучена классифицировать изображения по тысяче категорий, но вам столько категорий не нужно. Также вам нужны четко определенные категории.</span><span class="sxs-lookup"><span data-stu-id="274a5-159">The `Inception model` is trained to classify images into a thousand categories, but you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="274a5-160">Перейдем к этапу передачи (`transfer`) этого процесса передачи обучения (`transfer learning`).</span><span class="sxs-lookup"><span data-stu-id="274a5-160">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="274a5-161">Вы можете передать способность `Inception model` распознавать и классифицировать изображения в новые ограниченные категории своего классификатора изображений.</span><span class="sxs-lookup"><span data-stu-id="274a5-161">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>  

 <span data-ttu-id="274a5-162">Также вы можете переобучить последний слой такой модели с помощью набора из трех категорий:</span><span class="sxs-lookup"><span data-stu-id="274a5-162">You're going to retrain the final layer of that model using a set of three categories:</span></span>

* <span data-ttu-id="274a5-163">еда;</span><span class="sxs-lookup"><span data-stu-id="274a5-163">Food</span></span>
* <span data-ttu-id="274a5-164">игрушка;</span><span class="sxs-lookup"><span data-stu-id="274a5-164">Toy</span></span>
* <span data-ttu-id="274a5-165">прибор.</span><span class="sxs-lookup"><span data-stu-id="274a5-165">Appliance</span></span>

<span data-ttu-id="274a5-166">Ваш слой будет использовать [алгоритм мультиномиальной логистической регрессии](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) для поиска корректной категории за минимальное время.</span><span class="sxs-lookup"><span data-stu-id="274a5-166">Your layer uses a [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) to find the correct category as quickly as possible.</span></span> <span data-ttu-id="274a5-167">Для поиска ответа этот алгоритм выполняет классификацию на основе вероятностей, присваивая соответствующей категории значение единицы, а всем остальным — нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="274a5-167">This algorithm classifies using probabilities to determine the answer, giving a one value to the correct category and a zero value to the others.</span></span>  

### <a name="dataset"></a><span data-ttu-id="274a5-168">DataSet</span><span class="sxs-lookup"><span data-stu-id="274a5-168">DataSet</span></span>

<span data-ttu-id="274a5-169">Доступны два источника данных: файл `.tsv` и файлы образов.</span><span class="sxs-lookup"><span data-stu-id="274a5-169">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="274a5-170">Файл `tags.tsv` содержит два столбца: первый определен как `ImagePath`, а во втором указана метка `Label`, соответствующая изображению.</span><span class="sxs-lookup"><span data-stu-id="274a5-170">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="274a5-171">В примере файла ниже отсутствует строка заголовка. Сам файл выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="274a5-171">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="274a5-172">Изображения для обучения и тестирования расположены в папках ресурсов, которые вы скачали в виде ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="274a5-172">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="274a5-173">Эти изображения принадлежат Викискладу.</span><span class="sxs-lookup"><span data-stu-id="274a5-173">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="274a5-174">*[Викисклад](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), бесплатный репозиторий мультимедиа.*</span><span class="sxs-lookup"><span data-stu-id="274a5-174">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="274a5-175">Получено в 10:48 17 октября 2018 г. со страниц:</span><span class="sxs-lookup"><span data-stu-id="274a5-175">Retrieved 10:48, October 17, 2018 from:</span></span>  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a><span data-ttu-id="274a5-176">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="274a5-176">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="274a5-177">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="274a5-177">Create a project</span></span>

1. <span data-ttu-id="274a5-178">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="274a5-178">Open Visual Studio 2017.</span></span> <span data-ttu-id="274a5-179">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="274a5-179">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="274a5-180">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="274a5-180">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="274a5-181">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="274a5-181">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="274a5-182">В текстовое поле **Имя** введите TransferLearningTF и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="274a5-182">In the **Name** text box, type "TransferLearningTF" and then select the **OK** button.</span></span>

2. <span data-ttu-id="274a5-183">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="274a5-183">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="274a5-184">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="274a5-184">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="274a5-185">Выберите nuget.org в качестве источника пакета, откройте вкладку "Обзор" и выполните поиск **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="274a5-185">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span> <span data-ttu-id="274a5-186">Щелкните раскрывающийся список **Версия**, выберите пакет **0.10.0** в списке и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="274a5-186">Click on the **Version** drop-down, select the **0.10.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="274a5-187">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="274a5-187">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="274a5-188">Повторите эти шаги для **Microsoft.ML.ImageAnalytics версии 0.10.0** и **Microsoft.ML.TensorFlow версии 0.10.0**.</span><span class="sxs-lookup"><span data-stu-id="274a5-188">Repeat these steps for **Microsoft.ML.ImageAnalytics v0.10.0** and **Microsoft.ML.TensorFlow v0.10.0**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="274a5-189">В этом руководстве используются **Microsoft.ML версии 0.10.0**, **Microsoft.ML.ImageAnalytics версии 0.10.0** и **Microsoft.ML.TensorFlow версии 0.10.0**.</span><span class="sxs-lookup"><span data-stu-id="274a5-189">This tutorial uses **Microsoft.ML v0.10.0**, **Microsoft.ML.ImageAnalytics v0.10.0**, and **Microsoft.ML.TensorFlow v0.10.0**.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="274a5-190">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="274a5-190">Prepare your data</span></span>

1. <span data-ttu-id="274a5-191">Скачайте [ZIP-файл каталога с ресурсами проекта](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) и распакуйте его.</span><span class="sxs-lookup"><span data-stu-id="274a5-191">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

2. <span data-ttu-id="274a5-192">Скопируйте каталог `assets` в каталог проекта *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="274a5-192">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="274a5-193">Этот каталог и его подкаталоги содержат данные и файлы поддержки (за исключением модели Inception, которую вы скачаете и добавите на следующем шаге), необходимые для работы с этим руководством.</span><span class="sxs-lookup"><span data-stu-id="274a5-193">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

3. <span data-ttu-id="274a5-194">Скачайте [модель Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) и распакуйте ее.</span><span class="sxs-lookup"><span data-stu-id="274a5-194">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

4. <span data-ttu-id="274a5-195">Скопируйте содержание каталога `inception5h`, который вы распаковали, в каталог `assets\inputs-train\inception` проекта *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="274a5-195">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets\inputs-train\inception` directory.</span></span> <span data-ttu-id="274a5-196">Этот каталог содержит модель и дополнительные файлы поддержки, необходимые для работы с этим руководством, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="274a5-196">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Содержание каталога Inception](./media/image-classification/inception-files.png)

5. <span data-ttu-id="274a5-198">В обозревателе решений щелкните правой кнопкой мыши каждый файл в каталоге и подкаталогах ресурсов и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="274a5-198">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="274a5-199">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="274a5-199">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="274a5-200">Создание классов и определение путей</span><span class="sxs-lookup"><span data-stu-id="274a5-200">Create classes and define paths</span></span>

<span data-ttu-id="274a5-201">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="274a5-201">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

<span data-ttu-id="274a5-202">Создайте глобальные поля для хранения путей к различным ресурсам, а также глобальные переменные для значений `LabelTokey`, `ImageReal` и `PredictedLabelValue`:</span><span class="sxs-lookup"><span data-stu-id="274a5-202">Create global fields to hold the paths to the various assets, and global variables for the `LabelTokey`,`ImageReal`, and  `PredictedLabelValue`:</span></span>

* <span data-ttu-id="274a5-203">`_assetsPath` содержит путь к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="274a5-203">`_assetsPath` has the path to the assets.</span></span>
* <span data-ttu-id="274a5-204">`_trainTagsTsv` содержит путь к TSV-файлу с тегами данных изображения обучения.</span><span class="sxs-lookup"><span data-stu-id="274a5-204">`_trainTagsTsv` has the path to the training image data tags tsv file.</span></span>
* <span data-ttu-id="274a5-205">`_predictTagsTsv` содержит путь к TSV-файлу с тегами данных изображения прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="274a5-205">`_predictTagsTsv` has the path to the prediction image data tags tsv file.</span></span>
* <span data-ttu-id="274a5-206">`_trainImagesFolder` содержит путь к изображениям, используемым для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="274a5-206">`_trainImagesFolder` has the path to the images used to train the model.</span></span>
* <span data-ttu-id="274a5-207">`_predictImagesFolder` содержит путь к изображениям, классифицируемым обученной моделью.</span><span class="sxs-lookup"><span data-stu-id="274a5-207">`_predictImagesFolder` has the path to the images to be classified by the trained model.</span></span>
* <span data-ttu-id="274a5-208">`_inceptionPb` содержит путь к предварительно обученной модели Inception, которая используется для переобучения вашей модели.</span><span class="sxs-lookup"><span data-stu-id="274a5-208">`_inceptionPb` has the path to the pre-trained Inception model to be reused to retrain your model.</span></span>
* <span data-ttu-id="274a5-209">`_inputImageClassifierZip` содержит путь, из которого загружается обученная модель.</span><span class="sxs-lookup"><span data-stu-id="274a5-209">`_inputImageClassifierZip` has the path where the trained model is loaded from.</span></span>
* <span data-ttu-id="274a5-210">`_outputImageClassifierZip` содержит путь, по которому сохраняется обученная модель.</span><span class="sxs-lookup"><span data-stu-id="274a5-210">`_outputImageClassifierZip` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="274a5-211">`LabelTokey` — это значение `Label`, сопоставленное с ключом.</span><span class="sxs-lookup"><span data-stu-id="274a5-211">`LabelTokey` is the `Label` value mapped to a key.</span></span>
* <span data-ttu-id="274a5-212">`ImageReal` — это столбец, содержащий спрогнозированное значение изображения.</span><span class="sxs-lookup"><span data-stu-id="274a5-212">`ImageReal`  is the column containing the predicted image value.</span></span>
* <span data-ttu-id="274a5-213">`PredictedLabelValue` — это столбец, содержащий спрогнозированное значение метки.</span><span class="sxs-lookup"><span data-stu-id="274a5-213">`PredictedLabelValue` is the column containing the predicted label value.</span></span>

<span data-ttu-id="274a5-214">Добавьте следующий код в строку непосредственно над методом `Main`, чтобы указать эти пути и другие переменные:</span><span class="sxs-lookup"><span data-stu-id="274a5-214">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="274a5-215">Создайте несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="274a5-215">Create some classes for your input data, and predictions.</span></span> <span data-ttu-id="274a5-216">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="274a5-216">Add a new class to your project:</span></span>

1. <span data-ttu-id="274a5-217">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="274a5-217">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="274a5-218">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *ImageData.cs*.</span><span class="sxs-lookup"><span data-stu-id="274a5-218">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageData.cs*.</span></span> <span data-ttu-id="274a5-219">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="274a5-219">Then, select the **Add** button.</span></span>

    <span data-ttu-id="274a5-220">Файл *ImageData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="274a5-220">The *ImageData.cs* file opens in the code editor.</span></span> <span data-ttu-id="274a5-221">Добавьте следующую инструкцию `using` в начало файла *ImageData.cs*:</span><span class="sxs-lookup"><span data-stu-id="274a5-221">Add the following `using` statement to the top of *ImageData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

<span data-ttu-id="274a5-222">Удалите существующее определение класса и добавьте следующий код для класса `ImageData` в файл *ImageData.cs*:</span><span class="sxs-lookup"><span data-stu-id="274a5-222">Remove the existing class definition and add the following code for the `ImageData` class to the *ImageData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

<span data-ttu-id="274a5-223">`ImageData` является классом входных данных изображения и имеет следующие поля <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="274a5-223">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="274a5-224">`ImagePath` содержит имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="274a5-224">`ImagePath` contains the image file name.</span></span>
* <span data-ttu-id="274a5-225">`Label` содержит значение для метки изображения.</span><span class="sxs-lookup"><span data-stu-id="274a5-225">`Label` contains a value for the image label.</span></span>

<span data-ttu-id="274a5-226">Добавьте новый класс в свой проект для `ImagePrediction`:</span><span class="sxs-lookup"><span data-stu-id="274a5-226">Add a new class to your project for `ImagePrediction`:</span></span>

1. <span data-ttu-id="274a5-227">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="274a5-227">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="274a5-228">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *ImagePrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="274a5-228">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImagePrediction.cs*.</span></span> <span data-ttu-id="274a5-229">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="274a5-229">Then, select the **Add** button.</span></span>

    <span data-ttu-id="274a5-230">Файл *ImagePrediction.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="274a5-230">The *ImagePrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="274a5-231">Удалите обе инструкции `using` `System.Collections.Generic` и `System.Text` в начале файла *ImagePrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="274a5-231">Remove both the `System.Collections.Generic` and the `System.Text` `using` statements at the top of *ImagePrediction.cs*:</span></span>

<span data-ttu-id="274a5-232">Удалите существующее определение класса и добавьте следующий код с классом `ImagePrediction` в файл *ImagePrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="274a5-232">Remove the existing class definition and add the following code, which has the `ImagePrediction` class, to the *ImagePrediction.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

<span data-ttu-id="274a5-233">`ImagePrediction` является классом прогноза изображения и имеет следующие поля:</span><span class="sxs-lookup"><span data-stu-id="274a5-233">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

* <span data-ttu-id="274a5-234">`Score` содержит процентное значение достоверности для конкретной классификации изображения.</span><span class="sxs-lookup"><span data-stu-id="274a5-234">`Score` contains the confidence percentage for a given image classification.</span></span>
* <span data-ttu-id="274a5-235">`PredictedLabelValue` содержит значение для прогнозируемой метки классификации изображения.</span><span class="sxs-lookup"><span data-stu-id="274a5-235">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

<span data-ttu-id="274a5-236">Класс `ImagePrediction` используется для прогнозирования после обучения модели.</span><span class="sxs-lookup"><span data-stu-id="274a5-236">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="274a5-237">Он включает `string` (`ImagePath`) с путем к изображению.</span><span class="sxs-lookup"><span data-stu-id="274a5-237">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="274a5-238">`Label` используется для применения и переобучения модели.</span><span class="sxs-lookup"><span data-stu-id="274a5-238">The `Label` is used to reuse and retrain the model.</span></span> <span data-ttu-id="274a5-239">`PredictedLabelValue` используется для прогнозирования и оценки.</span><span class="sxs-lookup"><span data-stu-id="274a5-239">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="274a5-240">Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.</span><span class="sxs-lookup"><span data-stu-id="274a5-240">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="274a5-241">[Класс MLContext](xref:Microsoft.ML.MLContext) является отправной точкой для любых операций ML.NET. В результате инициализации класса `mlContext` создается среда ML.NET, которая может использоваться всеми объектами в рамках процесса создания модели.</span><span class="sxs-lookup"><span data-stu-id="274a5-241">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="274a5-242">По существу он аналогичен классу `DBContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="274a5-242">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="274a5-243">Инициализация переменных в методе Main</span><span class="sxs-lookup"><span data-stu-id="274a5-243">Initialize variables in Main</span></span>

<span data-ttu-id="274a5-244">Инициализируйте переменную `mlContext` с использованием нового экземпляра `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="274a5-244">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="274a5-245">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="274a5-245">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a><span data-ttu-id="274a5-246">Создание структуры для параметров по умолчанию</span><span class="sxs-lookup"><span data-stu-id="274a5-246">Create a struct for default parameters</span></span>

<span data-ttu-id="274a5-247">Модель Inception имеет несколько параметров по умолчанию, которые необходимо передать.</span><span class="sxs-lookup"><span data-stu-id="274a5-247">The Inception model has several default parameters you need to pass in.</span></span> <span data-ttu-id="274a5-248">Создайте структуру, чтобы сопоставить значения параметров по умолчанию с понятными именами, с помощью следующего кода сразу после метода `Main()`:</span><span class="sxs-lookup"><span data-stu-id="274a5-248">Create a struct to map the default parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="274a5-249">Создание служебного метода для отображения данных</span><span class="sxs-lookup"><span data-stu-id="274a5-249">Create a display utility method</span></span>

<span data-ttu-id="274a5-250">Для многократного создания пар данных изображения и связанных прогнозов, а также для их отображения не нужно дублировать код.</span><span class="sxs-lookup"><span data-stu-id="274a5-250">Pair and display the image data and the related predictions more than once, and you don't want to duplicate code.</span></span> <span data-ttu-id="274a5-251">Создайте служебный метод для отображения данных, чтобы обрабатывать связывание пар, отображение изображения и результатов прогнозов.</span><span class="sxs-lookup"><span data-stu-id="274a5-251">Create a display utility method to handle pairing and displaying the image and prediction results.</span></span>

<span data-ttu-id="274a5-252">Метод `PairAndDisplayResults()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="274a5-252">The `PairAndDisplayResults()` method executes the following tasks:</span></span>

* <span data-ttu-id="274a5-253">объединение данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="274a5-253">Combines data and predictions for reporting.</span></span>
* <span data-ttu-id="274a5-254">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="274a5-254">Displays the predicted results.</span></span>

<span data-ttu-id="274a5-255">Создайте метод `PairAndDisplayResults()` сразу после структуры `InceptionSettings` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="274a5-255">Create the `PairAndDisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

```csharp
private static void PairAndDisplayResults(IEnumerable<ImageNetData> imageData, IEnumerable<ImageNetPrediction> imagePredictionData)
{

}
```

<span data-ttu-id="274a5-256">Перед отображением результатов прогнозирования объедините `imageData` и `imagePrediction`, чтобы просмотреть исходное значение `Image Path` с прогнозируемой категорией изображения.</span><span class="sxs-lookup"><span data-stu-id="274a5-256">Before displaying the predicted results, combine the `imageData` and `imagePrediction` together to see the original `Image Path` with its predicted category.</span></span> <span data-ttu-id="274a5-257">В следующем коде для этого используется метод <xref:System.Linq.Enumerable.Zip%2A?displayProperty=nameWithType>, поэтому добавьте его в качестве первой строки метода `PairAndDisplayResults()`:</span><span class="sxs-lookup"><span data-stu-id="274a5-257">The following code uses the <xref:System.Linq.Enumerable.Zip%2A?displayProperty=nameWithType> method to make that happen, so add it as the first line of the `PairAndDisplayResults()` method:</span></span>

[!code-csharp[BuildImagePredictionPairs](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#BuildImagePredictionPairs)]

<span data-ttu-id="274a5-258">Теперь, когда вы объединили в один класс `imageData` и `imageData`, можно отобразить результаты с помощью метода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="274a5-258">Now that you've combined the `imageData` and `imageData` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

<span data-ttu-id="274a5-259">Вы вызовете метод `PairAndDisplayResults()` в следующих двух методах.</span><span class="sxs-lookup"><span data-stu-id="274a5-259">You'll call the `PairAndDisplayResults()` method in the next two methods.</span></span>

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="274a5-260">Создание служебного метода для TSV-файла</span><span class="sxs-lookup"><span data-stu-id="274a5-260">Create a .tsv file utility method</span></span>

<span data-ttu-id="274a5-261">Метод `ReadFromTsv()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="274a5-261">The `ReadFromTsv()` method executes the following tasks:</span></span>

* <span data-ttu-id="274a5-262">считывание файла `tags.tsv` с данными изображения;</span><span class="sxs-lookup"><span data-stu-id="274a5-262">Reads the image data `tags.tsv` file.</span></span>
* <span data-ttu-id="274a5-263">добавление пути файла к имени файла изображения;</span><span class="sxs-lookup"><span data-stu-id="274a5-263">Adds the file path to the image file name.</span></span>
* <span data-ttu-id="274a5-264">загрузка данных файла в объект IEnumerable `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="274a5-264">Loads the file data into an IEnumerable`ImageData` object.</span></span>

<span data-ttu-id="274a5-265">Создайте метод `ReadFromTsv()` сразу после метода `PairAndDisplayResults()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="274a5-265">Create the `ReadFromTsv()` method, just after the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

<span data-ttu-id="274a5-266">Указанный ниже код анализирует файл `tags.tsv`, после чего добавляет путь к файлу к имени файла изображения для свойства `ImagePath` и загружает его и `Label` в объект `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="274a5-266">The following code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span> <span data-ttu-id="274a5-267">Добавьте его в качестве первой строки метода `ReadFromTsv()`.</span><span class="sxs-lookup"><span data-stu-id="274a5-267">Add it as the first line of the `ReadFromTsv()` method.</span></span>  <span data-ttu-id="274a5-268">Вам понадобится полный путь к файлу для отображения результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="274a5-268">You need the fully qualified file path to display the prediction results.</span></span>

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
<span data-ttu-id="274a5-269">В ML.NET есть три основных понятия: [данные](../basic-concepts-model-training-in-mldotnet.md#data), [преобразователи](../basic-concepts-model-training-in-mldotnet.md#transformer) и [средства оценки](../basic-concepts-model-training-in-mldotnet.md#estimator).</span><span class="sxs-lookup"><span data-stu-id="274a5-269">There are three major concepts in ML.NET: [Data](../basic-concepts-model-training-in-mldotnet.md#data), [Transformers](../basic-concepts-model-training-in-mldotnet.md#transformer), and [Estimators](../basic-concepts-model-training-in-mldotnet.md#estimator).</span></span>

## <a name="reuse-and-tune-pre-trained-model"></a><span data-ttu-id="274a5-270">Повторное использование и настройка предварительно обученной модели</span><span class="sxs-lookup"><span data-stu-id="274a5-270">Reuse and tune pre-trained model</span></span>

<span data-ttu-id="274a5-271">В следующей строке кода в методе `Main()` добавьте приведенный ниже вызов метода `ReuseAndTuneInceptionModel()`:</span><span class="sxs-lookup"><span data-stu-id="274a5-271">Add the following call to the `ReuseAndTuneInceptionModel()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

<span data-ttu-id="274a5-272">Метод `ReuseAndTuneInceptionModel()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="274a5-272">The `ReuseAndTuneInceptionModel()` method executes the following tasks:</span></span>

* <span data-ttu-id="274a5-273">загрузка данных;</span><span class="sxs-lookup"><span data-stu-id="274a5-273">Loads the data</span></span>
* <span data-ttu-id="274a5-274">извлечение и преобразование данных;</span><span class="sxs-lookup"><span data-stu-id="274a5-274">Extracts and transforms the data.</span></span>
* <span data-ttu-id="274a5-275">оценка модели TensorFlow;</span><span class="sxs-lookup"><span data-stu-id="274a5-275">Scores the TensorFlow model.</span></span>
* <span data-ttu-id="274a5-276">настройка (переобучение) модели;</span><span class="sxs-lookup"><span data-stu-id="274a5-276">Tunes (retrains) the model.</span></span>
* <span data-ttu-id="274a5-277">отображение результатов модели;</span><span class="sxs-lookup"><span data-stu-id="274a5-277">Displays model results.</span></span>
* <span data-ttu-id="274a5-278">оценка итоговой модели;</span><span class="sxs-lookup"><span data-stu-id="274a5-278">Evaluates the model.</span></span>
* <span data-ttu-id="274a5-279">сохранение модели.</span><span class="sxs-lookup"><span data-stu-id="274a5-279">Saves the model.</span></span>

<span data-ttu-id="274a5-280">Создайте метод `ReuseAndTuneInceptionModel()` сразу после структуры `InceptionSettings` и непосредственно перед методом `PairAndDisplayResults()` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="274a5-280">Create the `ReuseAndTuneInceptionModel()` method, just after the `InceptionSettings` struct and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a><span data-ttu-id="274a5-281">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="274a5-281">Load the data</span></span>

<span data-ttu-id="274a5-282">Данные в ML.NET представлены [классом IDataView](xref:Microsoft.Data.DataView.IDataView).</span><span class="sxs-lookup"><span data-stu-id="274a5-282">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.Data.DataView.IDataView).</span></span> <span data-ttu-id="274a5-283">`IDataView` позволяет гибко и полно описывать табличные данные (числовые и текстовые).</span><span class="sxs-lookup"><span data-stu-id="274a5-283">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="274a5-284">Данные можно загружать в объект `IDataView` из текстового файла или в режиме реального времени (например, из базы данных SQL или файлов журнала).</span><span class="sxs-lookup"><span data-stu-id="274a5-284">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="274a5-285">Загрузите данные с помощью оболочки `MLContext.Data.ReadFromTextFile`.</span><span class="sxs-lookup"><span data-stu-id="274a5-285">Load the data using the `MLContext.Data.ReadFromTextFile` wrapper.</span></span> <span data-ttu-id="274a5-286">Добавьте в следующую строку метода `ReuseAndTuneInceptionModel()` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="274a5-286">Add the following code as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="274a5-287">Извлечение компонентов и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="274a5-287">Extract Features and transform the data</span></span>

<span data-ttu-id="274a5-288">Предварительная обработка и очистка данных — это очень важные задачи, которые нужно выполнить перед использованием набора данных для машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="274a5-288">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span>  <span data-ttu-id="274a5-289">Использование данных напрямую без этих задач моделирования может дать неправильные результаты.</span><span class="sxs-lookup"><span data-stu-id="274a5-289">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="274a5-290">Алгоритмы машинного обучения распознают данные с [присвоенными признаками](../resources/glossary.md#feature), поэтому при работе с глубокими нейронными сетями вам необходимо преобразовать изображения в подходящий для сети формат.</span><span class="sxs-lookup"><span data-stu-id="274a5-290">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, and when dealing with deep neural networks you must adapt the images to the format expected by the network.</span></span> <span data-ttu-id="274a5-291">Этот формат — [числовой вектор](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="274a5-291">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="274a5-292">После обучения и оценки создайте прогноз с помощью значений столбца **Label**.</span><span class="sxs-lookup"><span data-stu-id="274a5-292">After training and evaluation, predict with the **Label** column values.</span></span> <span data-ttu-id="274a5-293">Так как вы используете предварительно обученную модель, сопоставьте поля с новой моделью с помощью метода [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A).</span><span class="sxs-lookup"><span data-stu-id="274a5-293">As you're using a pre-trained model, map fields to the new model with the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method.</span></span> <span data-ttu-id="274a5-294">Этот метод преобразует `Label` в столбец с числовыми ключами (`LabelTokey`) и добавляет его в виде нового столбца набора данных.  Присвойте этому средству оценки `estimator` имя, так как вы также добавите к нему метод обучения.</span><span class="sxs-lookup"><span data-stu-id="274a5-294">This method transforms the `Label` into a numeric key type (`LabelTokey`) column and add it as new dataset column:  Name this `estimator` as you'll also add the trainer to it.</span></span> <span data-ttu-id="274a5-295">Добавьте следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="274a5-295">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

<span data-ttu-id="274a5-296">Ваше средство оценки обработки изображений использует средства присвоения признаков предварительно обученной [глубокой нейронной сети (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) для выделения признаков.</span><span class="sxs-lookup"><span data-stu-id="274a5-296">Your image processing estimator uses pre-trained [Deep Neural Network(DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizers for feature extraction.</span></span> <span data-ttu-id="274a5-297">При работе с глубокими нейронными сетями вам необходимо преобразовать изображения в подходящий для сети формат.</span><span class="sxs-lookup"><span data-stu-id="274a5-297">When dealing with deep neural networks, you  adapt the images to the expected network format.</span></span> <span data-ttu-id="274a5-298">По этой причине вам нужно использовать несколько преобразований изображений, чтобы вы могли предоставить модели данные изображений в подходящем формате:</span><span class="sxs-lookup"><span data-stu-id="274a5-298">This is the reason you use several image transforms to get the image data into the model's expected form:</span></span>

1. <span data-ttu-id="274a5-299">Изображения преобразования `LoadImages` загружаются в память как растровые изображения.</span><span class="sxs-lookup"><span data-stu-id="274a5-299">The `LoadImages`transform images are loaded in memory as a Bitmap type.</span></span>
2. <span data-ttu-id="274a5-300">Преобразование `Resize` изменяет размер изображений, так как предварительно обученная модель имеет определенные значения ширины и высоты изображений.</span><span class="sxs-lookup"><span data-stu-id="274a5-300">The `Resize` transform resizes the images as the pre-trained model has a defined input image width and height.</span></span>
3. <span data-ttu-id="274a5-301">Преобразование `ImagePixelExtractingEstimator` извлекает пиксели из входных изображений и преобразует их в числовой вектор.</span><span class="sxs-lookup"><span data-stu-id="274a5-301">The `ImagePixelExtractingEstimator` transform extracts the pixels from the input images and converts them into a numeric vector.</span></span>

<span data-ttu-id="274a5-302">Добавьте эти преобразования изображений в следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="274a5-302">Add these image transforms as the next lines of code:</span></span>

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

<span data-ttu-id="274a5-303">Компонент `TensorFlowTransform` выделяет указанные выходные данные (признаки изображения `Inception model``softmax2_pre_activation`) и присваивает набору данных оценку с помощью предварительно обученной модели `TensorFlow`.</span><span class="sxs-lookup"><span data-stu-id="274a5-303">The `TensorFlowTransform` extracts specified outputs (the `Inception model`'s image features `softmax2_pre_activation`), and scores a dataset using the pre-trained `TensorFlow` model.</span></span>

<span data-ttu-id="274a5-304">Узел `softmax2_pre_activation` обеспечивает поддержку модели, определяя классы изображений.</span><span class="sxs-lookup"><span data-stu-id="274a5-304">`softmax2_pre_activation` assists the model with determining which class the images belongs to.</span></span> <span data-ttu-id="274a5-305">Узел `softmax2_pre_activation` возвращает значение вероятности для каждой категории изображения, причем сумма всех таких вероятностей должна равняться 1.</span><span class="sxs-lookup"><span data-stu-id="274a5-305">`softmax2_pre_activation` returns a probability for each of the categories for an image, and all of those probabilities must add up to 1.</span></span> <span data-ttu-id="274a5-306">Предполагается, что изображение принадлежит только к одной категории, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="274a5-306">It assumes that an image will belong to only one category, as shown in the following example:</span></span>

| <span data-ttu-id="274a5-307">Класс</span><span class="sxs-lookup"><span data-stu-id="274a5-307">Class</span></span>         | <span data-ttu-id="274a5-308">Вероятность</span><span class="sxs-lookup"><span data-stu-id="274a5-308">Probability</span></span>   |
| ------------- | ------------- |
| `Food`        |  <span data-ttu-id="274a5-309">0,001</span><span class="sxs-lookup"><span data-stu-id="274a5-309">0.001</span></span>        |
| `Toy`         |  <span data-ttu-id="274a5-310">0,95</span><span class="sxs-lookup"><span data-stu-id="274a5-310">0.95</span></span>         |
| `Appliance`   |  <span data-ttu-id="274a5-311">0,06</span><span class="sxs-lookup"><span data-stu-id="274a5-311">0.06</span></span>         |

<span data-ttu-id="274a5-312">Добавьте `TensorFlowTransform` к `estimator` с помощью такой строки кода:</span><span class="sxs-lookup"><span data-stu-id="274a5-312">Append the `TensorFlowTransform` to the `estimator` with the following line of code:</span></span>

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a><span data-ttu-id="274a5-313">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="274a5-313">Choose a training algorithm</span></span>

<span data-ttu-id="274a5-314">Чтобы добавить алгоритм обучения, вызовите метод оболочки `mlContext.MulticlassClassification.Trainers.LogisticRegression()`.</span><span class="sxs-lookup"><span data-stu-id="274a5-314">To add the training algorithm, call the `mlContext.MulticlassClassification.Trainers.LogisticRegression()` wrapper method.</span></span>  <span data-ttu-id="274a5-315">Класс `LogisticRegression` добавляется в `estimator` и принимает признаки изображения Inception (`softmax2_pre_activation`) и вводные параметры `Label` для обучения на основе исторических данных.</span><span class="sxs-lookup"><span data-stu-id="274a5-315">The `LogisticRegression` is appended to the `estimator` and accepts the Inception image features (`softmax2_pre_activation`) and the `Label` input parameters to learn from the historic data.</span></span>  <span data-ttu-id="274a5-316">Добавьте метод обучения с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="274a5-316">Add the trainer with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

<span data-ttu-id="274a5-317">Вам также нужно сопоставить `predictedlabel` с `predictedlabelvalue`:</span><span class="sxs-lookup"><span data-stu-id="274a5-317">You also need to map the `predictedlabel` to the `predictedlabelvalue`:</span></span>

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

<span data-ttu-id="274a5-318">Метод `Fit()` обучает вашу модель с помощью предоставленного набора данных для обучения.</span><span class="sxs-lookup"><span data-stu-id="274a5-318">The `Fit()` method trains your model with the provided training dataset.</span></span> <span data-ttu-id="274a5-319">Он выполняет определения средства оценки `Estimator`, преобразовывая данные и применяя алгоритм обучения, а затем возвращает обученную модель, то есть `Transformer`.</span><span class="sxs-lookup"><span data-stu-id="274a5-319">It executes the `Estimator` definitions by transforming the data and applying the training, and it returns back the trained model, which is a `Transformer`.</span></span> <span data-ttu-id="274a5-320">Обучите модель на основе данных `Train` и получите обученную модель, добавив в метод `ReuseAndTuneInceptionModel()` следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="274a5-320">Fit the model to the `Train` data and return the trained model by adding the following as the next line of code in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

<span data-ttu-id="274a5-321">Метод [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) делает прогнозы для нескольких входных строк тестового набора данных.</span><span class="sxs-lookup"><span data-stu-id="274a5-321">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>  <span data-ttu-id="274a5-322">Преобразуйте данные `Training`, добавив в метод `ReuseAndTuneInceptionModel()` следующий код:</span><span class="sxs-lookup"><span data-stu-id="274a5-322">Transform the `Training` data by adding the following code to `ReuseAndTuneInceptionModel()`:</span></span>

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

<span data-ttu-id="274a5-323">Преобразуйте представления `DataViews` данных изображений и прогнозов в строго типизированные объекты `IEnumerables`, чтобы связать их для более удобного отображения.</span><span class="sxs-lookup"><span data-stu-id="274a5-323">Convert your image data and prediction `DataViews` into strongly-typed `IEnumerables` to pair for easier display.</span></span> <span data-ttu-id="274a5-324">Для этого воспользуйтесь методом `MLContext.CreateEnumerable()`, добавив следующий код:</span><span class="sxs-lookup"><span data-stu-id="274a5-324">Use the `MLContext.CreateEnumerable()` method to do that, using the following code:</span></span>

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

<span data-ttu-id="274a5-325">Вызовите метод `PairAndDisplayResults()`, чтобы связать и отобразить данные и прогнозы, в следующей строке в методе `ReuseAndTuneInceptionModel()`:</span><span class="sxs-lookup"><span data-stu-id="274a5-325">Call the `PairAndDisplayResults()` method to pair and display your data and predictions as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[CallPairAndDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallPairAndDisplayResults1)]

<span data-ttu-id="274a5-326">Получив прогноз, с помощью метода [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) вы сможете:</span><span class="sxs-lookup"><span data-stu-id="274a5-326">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

* <span data-ttu-id="274a5-327">оценить модель (сравнивает спрогнозированные значения с фактическим набором данных `Labels`);</span><span class="sxs-lookup"><span data-stu-id="274a5-327">Assesses the model (compares the predicted values with the actual dataset `Labels`).</span></span>

* <span data-ttu-id="274a5-328">получить метрики производительности модели.</span><span class="sxs-lookup"><span data-stu-id="274a5-328">Returns the model performance metrics.</span></span> 

<span data-ttu-id="274a5-329">В качестве следующей строки в методе `ReuseAndTuneInceptionModel()` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="274a5-329">Add the following code to the `ReuseAndTuneInceptionModel()` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

<span data-ttu-id="274a5-330">Для классификации изображений выполняется оценка следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="274a5-330">The following metrics are evaluated for image classification:</span></span>

* <span data-ttu-id="274a5-331">`Log-loss` — см. раздел [Логарифмические потери](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="274a5-331">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="274a5-332">Значение логарифмических потерь должно быть максимально близко к нулю.</span><span class="sxs-lookup"><span data-stu-id="274a5-332">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="274a5-333">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="274a5-333">`Per class Log-loss`.</span></span> <span data-ttu-id="274a5-334">Значение логарифмических потерь для каждого класса должно быть максимально близко к нулю.</span><span class="sxs-lookup"><span data-stu-id="274a5-334">You want per class Log-loss to be as close to zero as possible.</span></span>

<span data-ttu-id="274a5-335">Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:</span><span class="sxs-lookup"><span data-stu-id="274a5-335">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

<span data-ttu-id="274a5-336">Метод `mlContext.Model.Save` сохраняет обученную модель в ZIP-файле (в папке assets/outputs), который затем можно использовать в других приложениях .NET для создания прогнозов.</span><span class="sxs-lookup"><span data-stu-id="274a5-336">`mlContext.Model.Save` saves your trained model to a .zip file (in the "assets/outputs" folder), which can be used in other .NET applications to make predictions.</span></span> <span data-ttu-id="274a5-337">В качестве следующей строки в методе `ReuseAndTuneInceptionModel()` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="274a5-337">Add the following code to the `ReuseAndTuneInceptionModel()` method as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#SaveModel)]

## <a name="classify-images-with-a-loaded-model"></a><span data-ttu-id="274a5-338">Классификация изображений с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="274a5-338">Classify images with a loaded model</span></span>

<span data-ttu-id="274a5-339">Добавьте такой вызов в метод `ClassifyImages()` в следующей строке кода в методе `Main`:</span><span class="sxs-lookup"><span data-stu-id="274a5-339">Add the following call to the `ClassifyImages()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

<span data-ttu-id="274a5-340">Метод `ClassifyImages()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="274a5-340">The `ClassifyImages()` method executes the following tasks:</span></span>

* <span data-ttu-id="274a5-341">загрузка модели;</span><span class="sxs-lookup"><span data-stu-id="274a5-341">Loads the model.</span></span>
* <span data-ttu-id="274a5-342">считывание TSV-файла в интерфейс `IEnumerable`;</span><span class="sxs-lookup"><span data-stu-id="274a5-342">Reads .TSV file into `IEnumerable`.</span></span>
* <span data-ttu-id="274a5-343">создание прогноза для классификаций изображений на основе проверочных данных.</span><span class="sxs-lookup"><span data-stu-id="274a5-343">Predicts image classifications based on test data.</span></span>

<span data-ttu-id="274a5-344">Создайте метод `ClassifyImages()` сразу после метода `ReuseAndTuneInceptionModel()` и непосредственно перед методом `PairAndDisplayResults()` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="274a5-344">Create the `ClassifyImages()` method, just after the `ReuseAndTuneInceptionModel()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation)
{

}
```

<span data-ttu-id="274a5-345">Сначала загрузите сохраненную ранее модель, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="274a5-345">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadModel)]

<span data-ttu-id="274a5-346">Вызовите метод `ReadFromTsv()` для создания класса `IEnumerable<ImageData>`, который содержит абсолютный путь для каждого значения `ImagePath`.</span><span class="sxs-lookup"><span data-stu-id="274a5-346">Call the `ReadFromTsv()` method to create an `IEnumerable<ImageData>` class that contains the fully qualified path for each `ImagePath`.</span></span> <span data-ttu-id="274a5-347">Вам потребуется такой путь к файлу для связывания данных и результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="274a5-347">You need that file path to pair your data and prediction results.</span></span> <span data-ttu-id="274a5-348">Вам также нужно преобразовать класс `IEnumerable<ImageData>` в класс `IDataView`, который будет использоваться для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="274a5-348">You also need to convert the `IEnumerable<ImageData>` class to an `IDataView` that you will use to predict.</span></span> <span data-ttu-id="274a5-349">Добавьте такой код в следующие две строки в методе `ClassifyImages()`:</span><span class="sxs-lookup"><span data-stu-id="274a5-349">Add the following code as the next two lines in the `ClassifyImages()` method:</span></span>

[!code-csharp[ReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTSV)]

<span data-ttu-id="274a5-350">Как вы это уже сделали с данными изображения для обучения, создайте прогноз категории для проверочных данных изображения с помощью метода [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A).</span><span class="sxs-lookup"><span data-stu-id="274a5-350">As you did previously with the training image data, predict the category of the test image data using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method.</span></span> <span data-ttu-id="274a5-351">Добавьте следующий код в метод `ClassifyImages()`, чтобы создавать прогнозы и преобразовывать `predictions` `IDataView` в `IEnumerable` для связывания и отображения:</span><span class="sxs-lookup"><span data-stu-id="274a5-351">Add the following code to the `ClassifyImages()` method for the predictions and to convert the `predictions` `IDataView` into an `IEnumerable` for pairing and display:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

<span data-ttu-id="274a5-352">Чтобы связать и отобразить проверочные данные изображения и прогнозы, добавьте такой код для вызова ранее созданного метода `PairAndDisplayResults()` в следующую строку метода `ClassifyImages()`:</span><span class="sxs-lookup"><span data-stu-id="274a5-352">To pair and display your test image data and predictions, add the following code to call the `PairAndDisplayResults()` method previously created as the next line in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallPairAndDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallPairAndDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a><span data-ttu-id="274a5-353">Классификация отдельного изображения с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="274a5-353">Classify a single image with a loaded model</span></span>

<span data-ttu-id="274a5-354">Добавьте такой вызов в метод `ClassifySingleImage()` в следующей строке кода в методе `Main`:</span><span class="sxs-lookup"><span data-stu-id="274a5-354">Add the following call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

<span data-ttu-id="274a5-355">Метод `ClassifyImages()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="274a5-355">The `ClassifyImages()` method executes the following tasks:</span></span>

* <span data-ttu-id="274a5-356">загрузка модели;</span><span class="sxs-lookup"><span data-stu-id="274a5-356">Loads the model.</span></span>
* <span data-ttu-id="274a5-357">загрузка экземпляра `ImageData`;</span><span class="sxs-lookup"><span data-stu-id="274a5-357">Loads an `ImageData` instance.</span></span>
* <span data-ttu-id="274a5-358">создание прогноза для классификации изображений на основе проверочных данных.</span><span class="sxs-lookup"><span data-stu-id="274a5-358">Predicts image classification based on test data.</span></span>

<span data-ttu-id="274a5-359">Создайте метод `ClassifySingleImage()` сразу после метода `ClassifyImages()` и непосредственно перед методом `PairAndDisplayResults()` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="274a5-359">Create the `ClassifySingleImage()` method, just after the `ClassifyImages()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation)
{

}
```

<span data-ttu-id="274a5-360">Сначала загрузите сохраненную ранее модель, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="274a5-360">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadModel2)]

<span data-ttu-id="274a5-361">Создайте класс `ImageData`, который хранит абсолютный путь и имя файла изображения для одного значения `ImagePath`.</span><span class="sxs-lookup"><span data-stu-id="274a5-361">Create an `ImageData` class that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="274a5-362">Добавьте такой код в следующие строки в методе `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="274a5-362">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

<span data-ttu-id="274a5-363">Класс [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) — это удобный API, который создает прогноз на основе одного экземпляра данных.</span><span class="sxs-lookup"><span data-stu-id="274a5-363">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API that performs a prediction on a single instance of data.</span></span> <span data-ttu-id="274a5-364">Функция [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) создает прогноз по одному столбцу данных.</span><span class="sxs-lookup"><span data-stu-id="274a5-364">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span> <span data-ttu-id="274a5-365">Передайте значение `imageData` классу `PredictionEngine`, чтобы спрогнозировать категорию изображения, добавив следующий код в `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="274a5-365">Pass `imageData` to the `PredictionEngine` to predict the image category by adding the following code to `ClassifySingleImage()`:</span></span>

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

<span data-ttu-id="274a5-366">Отобразите результат прогнозирования с помощью следующей строки кода в методе `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="274a5-366">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a><span data-ttu-id="274a5-367">Результаты</span><span class="sxs-lookup"><span data-stu-id="274a5-367">Results</span></span>

<span data-ttu-id="274a5-368">Выполнив предыдущие шаги, запустите консольное приложение (CTRL+F5).</span><span class="sxs-lookup"><span data-stu-id="274a5-368">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="274a5-369">Результаты выполнения должны выглядеть примерно так, как указано ниже.</span><span class="sxs-lookup"><span data-stu-id="274a5-369">Your results should be similar to the following output.</span></span>  <span data-ttu-id="274a5-370">Кроме того, могут выводиться предупреждения или сообщения об обработке, но для удобства здесь мы убрали их.</span><span class="sxs-lookup"><span data-stu-id="274a5-370">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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
=============== Save model to local file ===============
Model saved: C:\Tutorials\TransferLearningTF\bin\Debug\netcoreapp2.2\assets\outputs\imageClassifier.zip
=============== Loading model ===============
Model loaded: C:\Tutorials\TransferLearningTF\bin\Debug\netcoreapp2.2\assets\outputs\imageClassifier.zip
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Loading model ===============
Model loaded: C:\Tutorials\TransferLearningTF\bin\Debug\netcoreapp2.2\assets\outputs\imageClassifier.zip
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379
Press any key to continue . . .
```

<span data-ttu-id="274a5-371">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="274a5-371">Congratulations!</span></span> <span data-ttu-id="274a5-372">Вы успешно создали модель машинного обучения для классификации изображений на основе предварительно обученной модели `TensorFlow` в ML.NET.</span><span class="sxs-lookup"><span data-stu-id="274a5-372">You've now successfully built a machine learning model for image classification by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="274a5-373">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="274a5-373">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="274a5-374">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="274a5-374">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="274a5-375">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="274a5-375">Understand the problem</span></span>
> * <span data-ttu-id="274a5-376">повторно использовать и настраивать предварительно обученную модель;</span><span class="sxs-lookup"><span data-stu-id="274a5-376">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="274a5-377">классифицировать изображения с помощью загруженной модели.</span><span class="sxs-lookup"><span data-stu-id="274a5-377">Classify images with a loaded model</span></span>

<span data-ttu-id="274a5-378">Ознакомьтесь с примерами Машинного обучения в репозитории GitHub, чтобы подробнее изучить расширенный пример классификации изображений.</span><span class="sxs-lookup"><span data-stu-id="274a5-378">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="274a5-379">Репозиторий GitHub dotnet/machinelearning-samples</span><span class="sxs-lookup"><span data-stu-id="274a5-379">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
