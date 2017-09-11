---
title: "Асинхронное серверное программирование. Руководство по C#"
description: "Изучите методы снижения рабочих нагрузок сервера с помощью технологий асинхронного программирования"
keywords: "C#, async, использование ресурсов ЦП, использование ресурсов сети"
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7402b29b-1093-456d-be4c-f60ecb8926bb
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 390d0eb2c8416165984ffe6c80ed6977e61a2845
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="-asynchronous-server-programming"></a><span data-ttu-id="59add-104">🔧 Асинхронное серверное программирование</span><span class="sxs-lookup"><span data-stu-id="59add-104">🔧 Asynchronous Server Programming</span></span>

> <span data-ttu-id="59add-105">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="59add-105">**Note**</span></span>
> 
> <span data-ttu-id="59add-106">Этот раздел еще не написан!</span><span class="sxs-lookup"><span data-stu-id="59add-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="59add-107">Мы будем рады получить ваши предложения, которые помогут нам определить вопросы, требующие рассмотрения, и подход.</span><span class="sxs-lookup"><span data-stu-id="59add-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="59add-108">Вы можете отслеживать состояние и оставлять предложения по этой [теме](https://github.com/dotnet/docs/issues/952) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="59add-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/952) at GitHub.</span></span>
> 
> <span data-ttu-id="59add-109">Чтобы просмотреть черновые варианты и наброски этого раздела, оставьте сообщение со своими контактными данными в соответствующей теме.</span><span class="sxs-lookup"><span data-stu-id="59add-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="59add-110">Узнать больше о том, как вы можете посодействовать, можно на сайте [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="59add-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

