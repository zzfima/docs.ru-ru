---
title: Пакеты приложений, ориентированных на облако
description: Создание архитектуры облачных приложений .NET для Azure | Пакеты облачных приложений машинного кода
ms.date: 06/30/2019
ms.openlocfilehash: 0c67035af08d3c337ff027f3742e1ce8a83f8d0f
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840745"
---
# <a name="cloud-native-application-bundles"></a><span data-ttu-id="46a4c-103">Пакеты приложений, ориентированных на облако</span><span class="sxs-lookup"><span data-stu-id="46a4c-103">Cloud Native Application Bundles</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="46a4c-104">Ключевым свойством облачных приложений является то, что они используют свойства облака для ускорения разработки.</span><span class="sxs-lookup"><span data-stu-id="46a4c-104">A key property of cloud-native applications is that they leverage the properties of the cloud to speed up development.</span></span> <span data-ttu-id="46a4c-105">Это часто означает, что в полном приложении используются различные виды технологий.</span><span class="sxs-lookup"><span data-stu-id="46a4c-105">This often means that a full application uses different kinds of technologies.</span></span> <span data-ttu-id="46a4c-106">Приложения могут поставляться в контейнерах DOCKER. Некоторые службы могут использовать функции Azure, тогда как другие могут работать непосредственно с виртуальными машинами, выделенными на больших серверах с аппаратным ускорением GPU.</span><span class="sxs-lookup"><span data-stu-id="46a4c-106">Applications may be shipped in Docker containers, some services may use Azure Functions while other parts may run directly on virtual machines allocated on large metal servers with hardware GPU acceleration.</span></span> <span data-ttu-id="46a4c-107">Ни одно из двух собственных приложений в облаке не одинаково, поэтому было сложно предоставить единый механизм для их отправки.</span><span class="sxs-lookup"><span data-stu-id="46a4c-107">No two cloud-native applications are the same, so it's been difficult to provide a single mechanism for shipping them.</span></span>

<span data-ttu-id="46a4c-108">Контейнеры DOCKER могут выполняться в Kubernetes с помощью диаграммы Helm для развертывания.</span><span class="sxs-lookup"><span data-stu-id="46a4c-108">The Docker containers may run on Kubernetes using a Helm Chart for deployment.</span></span> <span data-ttu-id="46a4c-109">Функции Azure можно выделить с помощью шаблонов terraform.</span><span class="sxs-lookup"><span data-stu-id="46a4c-109">The Azure Functions may be allocated using Terraform templates.</span></span> <span data-ttu-id="46a4c-110">Наконец, виртуальные машины могут быть выделены с помощью terraform, но созданы с помощью Ansible.</span><span class="sxs-lookup"><span data-stu-id="46a4c-110">Finally, the virtual machines may be allocated using Terraform but built out using Ansible.</span></span> <span data-ttu-id="46a4c-111">Это совершенно неэффективное внедрение технологий, и нет возможности упаковать их вместе в разумный пакет.</span><span class="sxs-lookup"><span data-stu-id="46a4c-111">This is a whole mess of technologies and there has been no way to package them all together into a reasonable package.</span></span> <span data-ttu-id="46a4c-112">До настоящего момента.</span><span class="sxs-lookup"><span data-stu-id="46a4c-112">Until now.</span></span>

<span data-ttu-id="46a4c-113">Облачные пакеты приложений (КНАБС) представляют собой совместную деятельность ряда компаний, таких как Microsoft, Docker и HashiCorp, для разработки спецификаций для упаковки распределенных приложений.</span><span class="sxs-lookup"><span data-stu-id="46a4c-113">Cloud Native Application Bundles (CNABs) are a joint effort of a number of community-minded companies such as Microsoft, Docker, and HashiCorp to develop a specification to package distributed applications.</span></span>

<span data-ttu-id="46a4c-114">Усилия были объявлены в декабре 2018, поэтому по-прежнему остается довольно много усилий, чтобы сделать работу с большим сообществом.</span><span class="sxs-lookup"><span data-stu-id="46a4c-114">The effort was announced in December of 2018, so there's still a fair bit of work to do to expose the effort to the greater community.</span></span> <span data-ttu-id="46a4c-115">Однако уже есть [Открытая спецификация](https://github.com/deislabs/cnab-spec) и эталонная реализация, известная как [сумку](https://duffle.sh/).</span><span class="sxs-lookup"><span data-stu-id="46a4c-115">However, there's already an [open specification](https://github.com/deislabs/cnab-spec) and a reference implementation known as [Duffle](https://duffle.sh/).</span></span> <span data-ttu-id="46a4c-116">Это средство, написанное на Go, является совместным усилиями между DOCKER и Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="46a4c-116">This tool, which was written in Go, is a joint effort between Docker and Microsoft.</span></span>

<span data-ttu-id="46a4c-117">КНАБС может содержать различные технологии установки.</span><span class="sxs-lookup"><span data-stu-id="46a4c-117">The CNABs can contain different kinds of installation technologies.</span></span> <span data-ttu-id="46a4c-118">Это позволяет Helm диаграммы, шаблоны terraform и Ansible модули PlayBook сосуществовать в одном пакете.</span><span class="sxs-lookup"><span data-stu-id="46a4c-118">This allows things like Helm Charts, Terraform templates, and Ansible Playbooks to coexist in the same package.</span></span> <span data-ttu-id="46a4c-119">После сборки пакеты являются автономными и переносимыми. их можно установить с USB-носителя.</span><span class="sxs-lookup"><span data-stu-id="46a4c-119">Once built, the packages are self-contained and portable; they can be installed from a USB stick.</span></span>  <span data-ttu-id="46a4c-120">Пакеты криптографически подписываются, чтобы убедиться, что они берутся из утвержденной им стороны.</span><span class="sxs-lookup"><span data-stu-id="46a4c-120">The packages are cryptographically signed to ensure they originate from the party they claim.</span></span>

<span data-ttu-id="46a4c-121">Ядром КНАБ является файл с именем `bundle.json`.</span><span class="sxs-lookup"><span data-stu-id="46a4c-121">The core of a CNAB is a file called `bundle.json`.</span></span> <span data-ttu-id="46a4c-122">Этот файл определяет содержимое пакета, terraform или изображения или что-либо другое.</span><span class="sxs-lookup"><span data-stu-id="46a4c-122">This file defines the contents of the bundle, be they Terraform or images or anything else.</span></span> <span data-ttu-id="46a4c-123">На рис. 11-9 определен КНАБ, вызывающий некоторые terraform.</span><span class="sxs-lookup"><span data-stu-id="46a4c-123">Figure 11-9 defines a CNAB that invokes some Terraform.</span></span> <span data-ttu-id="46a4c-124">Однако обратите внимание, что он фактически определяет изображение вызова, которое используется для вызова terraform.</span><span class="sxs-lookup"><span data-stu-id="46a4c-124">Notice, however, that it actually defines an invocation image that is used to invoke the Terraform.</span></span> <span data-ttu-id="46a4c-125">При создании пакета файл DOCKER, расположенный в каталоге *КНАБ* , встроен в образ DOCKER, который будет включен в пакет.</span><span class="sxs-lookup"><span data-stu-id="46a4c-125">When packaged up, the Docker file that is located in the *cnab* directory is built into a Docker image, which will be included in the bundle.</span></span> <span data-ttu-id="46a4c-126">Установка terraform в контейнер DOCKER в пакете означает, что пользователям не нужно устанавливать terraform на компьютере для запуска объединения.</span><span class="sxs-lookup"><span data-stu-id="46a4c-126">Having Terraform installed inside a Docker container in the bundle means that users don't need to have Terraform installed on their machine to run the bundling.</span></span>

```json
{
    "name": "terraform",
    "version": "0.1.0",
    "schemaVersion": "v1.0.0-WD",
    "parameters": {
        "backend": {
            "type": "boolean",
            "defaultValue": false,
            "destination": {
                "env": "TF_VAR_backend"
            }
        }
    },
    "invocationImages": [
        {
        "imageType": "docker",
        "image": "cnab/terraform:latest"
        }
    ],
    "credentials": {
        "tenant_id": {
            "env": "TF_VAR_tenant_id"
        },
        "client_id": {
            "env": "TF_VAR_client_id"
        },
        "client_secret": {
            "env": "TF_VAR_client_secret"
        },
        "subscription_id": {
            "env": "TF_VAR_subscription_id"
        },
        "ssh_authorized_key": {
            "env": "TF_VAR_ssh_authorized_key"
        }
    },
    "actions": {
        "status": {
            "modifies": true
        }
    }
}
```

<span data-ttu-id="46a4c-127">**Рис. 11-13** . пример файла terraform</span><span class="sxs-lookup"><span data-stu-id="46a4c-127">**Figure 11-13** - An example Terraform file</span></span>

<span data-ttu-id="46a4c-128">`bundle.json` также определяет набор параметров, которые передаются в terraform.</span><span class="sxs-lookup"><span data-stu-id="46a4c-128">The `bundle.json` also defines a set of parameters that are passed down into the Terraform.</span></span> <span data-ttu-id="46a4c-129">Параметризация пакета позволяет устанавливать в различных средах.</span><span class="sxs-lookup"><span data-stu-id="46a4c-129">Parameterization of the bundle allows for installation in a variety of different environments.</span></span>

<span data-ttu-id="46a4c-130">Формат КНАБ также является гибким, что позволяет использовать его в любом облаке.</span><span class="sxs-lookup"><span data-stu-id="46a4c-130">The CNAB format is also flexible, allowing it to be used against any cloud.</span></span> <span data-ttu-id="46a4c-131">Его можно использовать и в локальных решениях, таких как [OpenStack](https://www.openstack.org/).</span><span class="sxs-lookup"><span data-stu-id="46a4c-131">It can even be used against on-premises solutions such as [OpenStack](https://www.openstack.org/).</span></span>

## <a name="devops-decisions"></a><span data-ttu-id="46a4c-132">DevOps решения</span><span class="sxs-lookup"><span data-stu-id="46a4c-132">DevOps Decisions</span></span>

<span data-ttu-id="46a4c-133">В DevOps пространстве есть много замечательных средств, а также еще более потрясающие книги и документы о том, как их можно достичь.</span><span class="sxs-lookup"><span data-stu-id="46a4c-133">There are so many great tools in the DevOps space these days and even more fantastic books and papers on how to succeed.</span></span> <span data-ttu-id="46a4c-134">Чтобы приступить к работе в DevOps, можно перейти к [проекту Phoenix](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), который следует за преобразованием вымышленной компании из Нупс в DevOps.</span><span class="sxs-lookup"><span data-stu-id="46a4c-134">A favorite book to get started on the DevOps journey is [The Phoenix Project](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), which follows the transformation of a fictional company from NoOps to DevOps.</span></span> <span data-ttu-id="46a4c-135">Одна из них: DevOps больше не является «полезной» при развертывании сложных облачных приложений в машинном код.</span><span class="sxs-lookup"><span data-stu-id="46a4c-135">One thing is for certain: DevOps is no longer a "nice to have" when deploying complex, Cloud Native Applications.</span></span> <span data-ttu-id="46a4c-136">Это требование, и его следует планировать и перенаследовать в начале любого проекта.</span><span class="sxs-lookup"><span data-stu-id="46a4c-136">It's a requirement and should be planned for and resourced at the start of any project.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="46a4c-137">Назад</span><span class="sxs-lookup"><span data-stu-id="46a4c-137">Previous</span></span>](infrastructure-as-code.md)
