---
title: Автоматизированное машинное обучение в ML.NET
description: Общие сведения об автоматическом выборе и обучении модели
author: natke
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
ms.openlocfilehash: 39e454d67f60280c6a43e3b80d788d873345ab77
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307377"
---
# <a name="automated-machine-learning-with-mlnet"></a><span data-ttu-id="19d6c-103">Автоматизированное машинное обучение в ML.NET</span><span class="sxs-lookup"><span data-stu-id="19d6c-103">Automated machine learning with ML.NET</span></span>

<span data-ttu-id="19d6c-104">Автоматизированное машинное обучение — это функция ML.NET для автоматического выбора и обучения модели.</span><span class="sxs-lookup"><span data-stu-id="19d6c-104">Automated machine learning is a feature of ML.NET that performs automatic model selection and training.</span></span> <span data-ttu-id="19d6c-105">Пользователь указывает задачу машинного обучения и предоставляет набор данных, а автоматизированное машинное обучение выбирает модели с оптимальными показателями.</span><span class="sxs-lookup"><span data-stu-id="19d6c-105">You specify the machine learning task and supply a dataset, and automated ML chooses the model with the best metrics.</span></span> <span data-ttu-id="19d6c-106">Будут доступны следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="19d6c-106">It outputs:</span></span>
- <span data-ttu-id="19d6c-107">файл модели, который можно загрузить в приложение для прогнозирования;</span><span class="sxs-lookup"><span data-stu-id="19d6c-107">a model file that can be loaded into your prediction application</span></span>
- <span data-ttu-id="19d6c-108">код приложения для прогнозирования;</span><span class="sxs-lookup"><span data-stu-id="19d6c-108">application code to make predictions</span></span>
- <span data-ttu-id="19d6c-109">исходный код, используемый для выбора компонентов и обучения модели (чтобы понять модель).</span><span class="sxs-lookup"><span data-stu-id="19d6c-109">the source code used for feature selection and model training (to understand the model)</span></span>

> [!NOTE]
> <span data-ttu-id="19d6c-110">Эта функция сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="19d6c-110">This feature is currently in Preview, and material may be subject to change.</span></span> 

<span data-ttu-id="19d6c-111">В настоящее время автоматизированное машинное обучение ограничено выполнением [задач](resources/tasks.md) двоичной классификации, многоклассовой классификации и регрессии.</span><span class="sxs-lookup"><span data-stu-id="19d6c-111">Automated ML is currently limited to the machine learning [tasks](resources/tasks.md) of binary classification, multiclass classification, and regression.</span></span> <span data-ttu-id="19d6c-112">Другие задачи машинного обучения будут поддерживаться в будущих выпусках.</span><span class="sxs-lookup"><span data-stu-id="19d6c-112">The other machine learning tasks will be supported in future releases.</span></span>

<span data-ttu-id="19d6c-113">Автоматизированное машинное обучение можно использовать тремя способами:</span><span class="sxs-lookup"><span data-stu-id="19d6c-113">There are three ways to use automated ML:</span></span>
1. <span data-ttu-id="19d6c-114">в командной строке с помощью [ML.NET CLI](automate-training-with-cli.md);</span><span class="sxs-lookup"><span data-stu-id="19d6c-114">On the command line, with the [ML.NET CLI](automate-training-with-cli.md)</span></span>
1. <span data-ttu-id="19d6c-115">в приложении с помощью [API автоматизированного машинного обучения](how-to-guides/how-to-use-the-automl-api.md);</span><span class="sxs-lookup"><span data-stu-id="19d6c-115">Via an application, with the [automated ML API](how-to-guides/how-to-use-the-automl-api.md)</span></span>
1. <span data-ttu-id="19d6c-116">в графическом пользовательском интерфейсе с помощью построителя моделей ML.NET.</span><span class="sxs-lookup"><span data-stu-id="19d6c-116">With a graphical user interface, with the ML.NET Model Builder</span></span>
