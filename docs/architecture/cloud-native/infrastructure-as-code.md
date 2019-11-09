---
title: Инфраструктура как код
description: Создание архитектуры облачных приложений .NET для Azure | Инфраструктура как код
ms.date: 06/30/2019
ms.openlocfilehash: 3957da68ac28774f899f49fb181a29c2435902f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841783"
---
# <a name="infrastructure-as-code"></a><span data-ttu-id="082e5-103">Инфраструктура как код</span><span class="sxs-lookup"><span data-stu-id="082e5-103">Infrastructure as code</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="082e5-104">Облачные приложения обычно используют все виды компонентов PaaS (платформа как услуга).</span><span class="sxs-lookup"><span data-stu-id="082e5-104">Cloud-native applications tend to make use of all sorts of fantastic platform as a service (PaaS) components.</span></span> <span data-ttu-id="082e5-105">На облачной платформе, такой как Azure, эти компоненты могут включать такие функции, как хранилище, служебная шина и служба SignalR.</span><span class="sxs-lookup"><span data-stu-id="082e5-105">On a cloud platform like Azure, these components might include things like storage, Service Bus, and the SignalR service.</span></span> <span data-ttu-id="082e5-106">По мере того, как приложения становятся более сложными, количество используемых этих служб, вероятно, будет расти.</span><span class="sxs-lookup"><span data-stu-id="082e5-106">As applications become more complicated, the number of these services in use is likely to grow.</span></span> <span data-ttu-id="082e5-107">Так же, как непрерывная доставка изменяла традиционную модель развертывания в среде вручную, быстрый темп изменений также нарушал модель централизованной ИТ-группы для управления средами.</span><span class="sxs-lookup"><span data-stu-id="082e5-107">Just as how continuous delivery broke the traditional model of deploying to an environment manually, the rapid pace of change also broke the model of having a centralized IT group manage environments.</span></span>

<span data-ttu-id="082e5-108">Среда разработки может также быть автоматизирована.</span><span class="sxs-lookup"><span data-stu-id="082e5-108">Building environments can, and should, also be automated.</span></span> <span data-ttu-id="082e5-109">Существует широкий спектр хорошо продуманных средств, которые могут упростить процесс.</span><span class="sxs-lookup"><span data-stu-id="082e5-109">There's a wide range of well thought out tools that can make the process easy.</span></span>

## <a name="azure-resource-manager-templates"></a><span data-ttu-id="082e5-110">Шаблоны Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="082e5-110">Azure Resource Manager templates</span></span>

<span data-ttu-id="082e5-111">Шаблоны Azure Resource Manager — это язык на основе JSON для определения различных ресурсов в Azure.</span><span class="sxs-lookup"><span data-stu-id="082e5-111">Azure Resource Manager templates are a JSON-based language for defining various resources in Azure.</span></span> <span data-ttu-id="082e5-112">Основная схема выглядит примерно так, как показано на рис. 11-10.</span><span class="sxs-lookup"><span data-stu-id="082e5-112">The basic schema looks something like Figure 11-10.</span></span>

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
  "contentVersion": "",
  "apiProfile": "",
  "parameters": {  },
  "variables": {  },
  "functions": [  ],
  "resources": [  ],
  "outputs": {  }
}
```

<span data-ttu-id="082e5-113">**Рис. 11-10** . схема для шаблона диспетчер ресурсов</span><span class="sxs-lookup"><span data-stu-id="082e5-113">**Figure 11-10** - The schema for a Resource Manager template</span></span>

<span data-ttu-id="082e5-114">В этом шаблоне можно определить контейнер хранилища в разделе ресурсов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="082e5-114">Within this template, one might define a storage container inside the resources section like so:</span></span>

```json
"resources": [
    {
      "type": "Microsoft.Storage/storageAccounts",
      "name": "[variables('storageAccountName')]",
      "location": "[parameters('location')]",
      "apiVersion": "2018-07-01",
      "sku": {
        "name": "[parameters('storageAccountType')]"
      },
      "kind": "StorageV2",
      "properties": {}
    }
  ],
```

<span data-ttu-id="082e5-115">**Рис. 11-11** . пример учетной записи хранения, определенной в шаблоне диспетчер ресурсов</span><span class="sxs-lookup"><span data-stu-id="082e5-115">**Figure 11-11** - An example of a storage account defined in a Resource Manager template</span></span>

<span data-ttu-id="082e5-116">Шаблоны можно параметризованными, чтобы один шаблон можно было использовать повторно с разными параметрами для определения разработки, контроля качества и рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="082e5-116">The templates can be parameterized so that one template can be reused with different settings to define development, QA, and production environments.</span></span> <span data-ttu-id="082e5-117">Это помогает избежать непредвиденных сюрпризов при переходе на более высокую среду, которая настроена иначе, чем в более низких средах.</span><span class="sxs-lookup"><span data-stu-id="082e5-117">This helps eliminate surprises when migrating to a higher environment that is set up differently from the lower environments.</span></span> <span data-ttu-id="082e5-118">Ресурсы, определенные в шаблоне, обычно создаются в одной группе ресурсов в Azure (можно определить несколько групп ресурсов в одном шаблоне диспетчер ресурсов, но нередко).</span><span class="sxs-lookup"><span data-stu-id="082e5-118">The resources defined in a template are typically all created within a single resource group on Azure (it's possible to define multiple resource groups in a single Resource Manager template but unusual).</span></span> <span data-ttu-id="082e5-119">Это позволяет легко удалить среду, просто удалив группу ресурсов в целом.</span><span class="sxs-lookup"><span data-stu-id="082e5-119">This makes it very easy to delete an environment by just deleting the resource group as a whole.</span></span> <span data-ttu-id="082e5-120">Анализ затрат также может выполняться на уровне группы ресурсов, что позволяет быстро учитывать объем данных каждой среды.</span><span class="sxs-lookup"><span data-stu-id="082e5-120">Cost analysis can also be run at the resource group level, allowing for quick accounting of how much each environment is costing.</span></span>

<span data-ttu-id="082e5-121">Существует множество примеров шаблонов, определенных в проекте [шаблонов](https://github.com/Azure/azure-quickstart-templates) быстрого запуска Azure на сайте GitHub, которые будут подниматься при запуске нового шаблона или добавлении к существующему.</span><span class="sxs-lookup"><span data-stu-id="082e5-121">There are many example templates defined in the [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) project on GitHub that will give a leg up when starting on a new template or adding to an existing one.</span></span>

<span data-ttu-id="082e5-122">Шаблоны диспетчер ресурсов могут выполняться различными способами.</span><span class="sxs-lookup"><span data-stu-id="082e5-122">Resource Manager templates can be run in a variety of ways.</span></span> <span data-ttu-id="082e5-123">Возможно, самый простой способ — просто вставить их в портал Azure.</span><span class="sxs-lookup"><span data-stu-id="082e5-123">Perhaps the simplest way is to simply paste them into the Azure portal.</span></span> <span data-ttu-id="082e5-124">Для экспериментальных развертываний этот метод может быть очень быстрым.</span><span class="sxs-lookup"><span data-stu-id="082e5-124">For experimental deployments, this method can be very quick.</span></span> <span data-ttu-id="082e5-125">Они также могут выполняться как часть процесса сборки или выпуска в Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="082e5-125">They can also be run as part of a build or release process in Azure DevOps.</span></span> <span data-ttu-id="082e5-126">Существуют задачи, которые будут использовать подключения к Azure для запуска шаблонов.</span><span class="sxs-lookup"><span data-stu-id="082e5-126">There are tasks that will leverage connections into Azure to run the templates.</span></span> <span data-ttu-id="082e5-127">Изменения шаблонов диспетчер ресурсов применяются постепенно, то есть для добавления нового ресурса необходимо просто добавить его в шаблон.</span><span class="sxs-lookup"><span data-stu-id="082e5-127">Changes to Resource Manager templates are applied incrementally, meaning that to add a new resource requires just adding it to the template.</span></span> <span data-ttu-id="082e5-128">Инструментарий будет выполнять сравнение текущей группы ресурсов с требуемой группой ресурсов, определенной в шаблоне.</span><span class="sxs-lookup"><span data-stu-id="082e5-128">The tooling will handle diffing the current resource group with the desired resource group defined in the template.</span></span> <span data-ttu-id="082e5-129">Ресурсы будут созданы или изменены так, чтобы они совпадали с тем, что определено в шаблоне.</span><span class="sxs-lookup"><span data-stu-id="082e5-129">Resources will then be created or altered so they match what is defined in the template.</span></span>  

## <a name="terraform"></a><span data-ttu-id="082e5-130">Terraform</span><span class="sxs-lookup"><span data-stu-id="082e5-130">Terraform</span></span>

<span data-ttu-id="082e5-131">Неудобство использования шаблонов диспетчер ресурсов заключается в том, что они относятся только к облаку Azure.</span><span class="sxs-lookup"><span data-stu-id="082e5-131">A perceived disadvantage of Resource Manager templates is that they are specific to the Azure cloud.</span></span> <span data-ttu-id="082e5-132">Создавать приложения, которые включают ресурсы из нескольких облаков, нередко, но в тех случаях, когда предприятие полагается на впечатляющая, стоимость поддержки нескольких облаков может быть целесообразной.</span><span class="sxs-lookup"><span data-stu-id="082e5-132">It's unusual to create applications that include resources from more than one cloud, but in cases where the business relies on spectacular uptime, the cost of supporting multiple clouds might be worthwhile.</span></span> <span data-ttu-id="082e5-133">Если существует один язык шаблонов, который можно использовать в каждом облаке, он также позволит повысить уровень переносимости навыков разработки.</span><span class="sxs-lookup"><span data-stu-id="082e5-133">If there were one templating language that could be used across every cloud, then it would also allow for developer skills to be much more portable.</span></span>

<span data-ttu-id="082e5-134">Существует несколько технологий, которые делают именно это!</span><span class="sxs-lookup"><span data-stu-id="082e5-134">Several technologies exist which do just that!</span></span> <span data-ttu-id="082e5-135">Наиболее зрелое предложение в этой области называется [terraform](https://www.terraform.io/).</span><span class="sxs-lookup"><span data-stu-id="082e5-135">The most mature offering in that space is known as [Terraform](https://www.terraform.io/).</span></span> <span data-ttu-id="082e5-136">Terraform поддерживает все крупные облачные проигрыватели, такие как Azure, Google Cloud Platform, AWS и Аликлауд, а также десятки дополнительных игроков, таких как Heroku и Дигиталоцеан.</span><span class="sxs-lookup"><span data-stu-id="082e5-136">Terraform supports every major cloud player such as Azure, Google Cloud Platform, AWS, and AliCloud, and it also supports dozens of minor players such as Heroku and DigitalOcean.</span></span> <span data-ttu-id="082e5-137">Вместо использования JSON в качестве языка определения шаблона он использует немного более сжатый YAML.</span><span class="sxs-lookup"><span data-stu-id="082e5-137">Instead of using JSON as the template definition language, it uses the slightly more terse YAML.</span></span>

<span data-ttu-id="082e5-138">Пример файла terraform, который делает то же, что и предыдущий шаблон диспетчер ресурсов (рис. 11-11), показан на рис. 11-12:</span><span class="sxs-lookup"><span data-stu-id="082e5-138">An example Terraform file that does the same as the previous Resource Manager template (Figure 11-11) is shown in Figure 11-12:</span></span>

```terraform
provider "azurerm" {
  version = "=1.28.0"
}

resource "azurerm_resource_group" "test" {
  name     = "production"
  location = "West US"
}

resource "azurerm_storage_account" "testsa" {
  name                     = "${var.storageAccountName}"
  resource_group_name      = "${azurerm_resource_group.testrg.name}"
  location                 = "${var.region}"
  account_tier             = "${var.tier}"
  account_replication_type = "${var.replicationType}"

}
```

<span data-ttu-id="082e5-139">**Рис. 11-12** . пример шаблона диспетчер ресурсов</span><span class="sxs-lookup"><span data-stu-id="082e5-139">**Figure 11-12** - An example of a Resource Manager template</span></span>

<span data-ttu-id="082e5-140">Terraform позволяет лучше предоставлять разумные сообщения об ошибках, когда ресурс не может быть развернут из-за ошибки в шаблоне.</span><span class="sxs-lookup"><span data-stu-id="082e5-140">Terraform does a better job of providing sensible error messages when a resource can't be deployed because of an error in the template.</span></span> <span data-ttu-id="082e5-141">Это область, где диспетчер ресурсов шаблоны имеют некоторые текущие проблемы.</span><span class="sxs-lookup"><span data-stu-id="082e5-141">This is an area where Resource Manager templates have some ongoing challenges.</span></span> <span data-ttu-id="082e5-142">Также есть очень удобная задача проверки, которую можно использовать на этапе сборки для перехвата ошибок шаблона на раннем этапе.</span><span class="sxs-lookup"><span data-stu-id="082e5-142">There's also a very handy validate task that can be used in the build phase to catch template errors early.</span></span>

<span data-ttu-id="082e5-143">Как и в случае с шаблонами диспетчер ресурсов, для развертывания шаблонов terraform можно использовать программы командной строки.</span><span class="sxs-lookup"><span data-stu-id="082e5-143">As with Resource Manager templates, there are command-line tools that can be used to deploy Terraform templates.</span></span> <span data-ttu-id="082e5-144">Кроме того, в Azure Pipelines есть задачи, созданные сообществом, которые могут проверять и применять шаблоны terraform.</span><span class="sxs-lookup"><span data-stu-id="082e5-144">There are also community-created tasks in Azure Pipelines that can validate and apply Terraform templates.</span></span>

<span data-ttu-id="082e5-145">В случае, если шаблон terraform или диспетчер ресурсов выводит интересные значения, такие как строка подключения к вновь созданной базе данных, они могут быть захвачены в конвейере сборки и использованы в последующих задачах.</span><span class="sxs-lookup"><span data-stu-id="082e5-145">In the event that the Terraform or Resource Manager template outputs interesting values such as the connection string to a newly created database they can be captured in the build pipeline and used in subsequent tasks.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="082e5-146">[Назад](devops.md)
>[Вперед](application-bundles.md)</span><span class="sxs-lookup"><span data-stu-id="082e5-146">[Previous](devops.md)
[Next](application-bundles.md)</span></span>
