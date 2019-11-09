---
title: Масштабирование облачных приложений
description: Масштабирование облачных приложений с помощью службы Azure Kubernetes и функций Azure для удовлетворения потребностей пользователей с учетом экономичного способа.
ms.date: 09/23/2019
ms.openlocfilehash: 5f4aac5804c5498c331787083c943a6ea1b69748
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841033"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="86e79-103">Масштабирование облачных приложений</span><span class="sxs-lookup"><span data-stu-id="86e79-103">Scaling cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="86e79-104">Одним из наиболее часто похвалу преимуществ перехода на облачную среду размещения является масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="86e79-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="86e79-105">Масштабируемость или возможность приложения принимать дополнительную нагрузку, не происходит чрезмерного производительность каждого пользователя, чаще всего достигается за счет разбиения приложений на небольшие части, которые могут предоставлять все необходимые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="86e79-105">Scalability, or the ability for an application to accept additional user load without unduly degrading performance for each user, is most often achieved by breaking up applications into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="86e79-106">В этой главе представлены технологии, позволяющие выполнять масштабирование облачных приложений в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="86e79-106">In this chapter, we introduce the technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="86e79-107">К этим технологиям относятся:</span><span class="sxs-lookup"><span data-stu-id="86e79-107">These technologies include:</span></span>

- <span data-ttu-id="86e79-108">Контейнеры</span><span class="sxs-lookup"><span data-stu-id="86e79-108">Containers</span></span>
- <span data-ttu-id="86e79-109">Оркестраторы</span><span class="sxs-lookup"><span data-stu-id="86e79-109">Orchestrators</span></span>
- <span data-ttu-id="86e79-110">Бессерверные вычисления</span><span class="sxs-lookup"><span data-stu-id="86e79-110">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="86e79-111">[Назад](centralized-configuration.md)
>[Вперед](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="86e79-111">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
