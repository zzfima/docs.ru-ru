---
title: Доступ к веб-службам приложения
ms.date: 07/20/2015
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
ms.openlocfilehash: ad616bd46f92261ec5ad6ae81d0db48138631ed1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349229"
---
# <a name="accessing-application-web-services-visual-basic"></a><span data-ttu-id="e9a9a-102">Доступ к веб-службам приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9a9a-102">Accessing Application Web Services (Visual Basic)</span></span>

<span data-ttu-id="e9a9a-103">Объект `My.WebServices` предоставляет экземпляр каждой веб-службы, на которую ссылается текущий проект.</span><span class="sxs-lookup"><span data-stu-id="e9a9a-103">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="e9a9a-104">Каждый экземпляр создается по запросу.</span><span class="sxs-lookup"><span data-stu-id="e9a9a-104">Each instance is instantiated on demand.</span></span> <span data-ttu-id="e9a9a-105">Доступ к этим веб-службам можно получить через свойства объекта `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="e9a9a-105">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="e9a9a-106">Имя свойства совпадает с именем веб-службы, к которой обращается свойство.</span><span class="sxs-lookup"><span data-stu-id="e9a9a-106">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="e9a9a-107">Любой класс, наследуемый от <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>, является веб-службой.</span><span class="sxs-lookup"><span data-stu-id="e9a9a-107">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span>

## <a name="tasks"></a><span data-ttu-id="e9a9a-108">Задачи</span><span class="sxs-lookup"><span data-stu-id="e9a9a-108">Tasks</span></span>

<span data-ttu-id="e9a9a-109">В следующей таблице перечислены возможные способы доступа к веб-службам, на которые ссылается приложение.</span><span class="sxs-lookup"><span data-stu-id="e9a9a-109">The following table lists possible ways to access Web services referenced by an application.</span></span>

|<span data-ttu-id="e9a9a-110">Кому</span><span class="sxs-lookup"><span data-stu-id="e9a9a-110">To</span></span>|<span data-ttu-id="e9a9a-111">См.</span><span class="sxs-lookup"><span data-stu-id="e9a9a-111">See</span></span>|
|---|---|
|<span data-ttu-id="e9a9a-112">Вызов веб-службы</span><span class="sxs-lookup"><span data-stu-id="e9a9a-112">Call a Web service</span></span>|[<span data-ttu-id="e9a9a-113">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="e9a9a-113">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)|
|<span data-ttu-id="e9a9a-114">Вызов веб-службы в асинхронном режиме и обработка события при его завершении</span><span class="sxs-lookup"><span data-stu-id="e9a9a-114">Call a Web service asynchronously and handle an event when it completes</span></span>|[<span data-ttu-id="e9a9a-115">Практическое руководство. Асинхронный вызов веб-службы</span><span class="sxs-lookup"><span data-stu-id="e9a9a-115">How to: Call a Web Service Asynchronously</span></span>](../../../visual-basic/developing-apps/programming/how-to-call-a-web-service-asynchronously.md)|

## <a name="see-also"></a><span data-ttu-id="e9a9a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e9a9a-116">See also</span></span>

- [<span data-ttu-id="e9a9a-117">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="e9a9a-117">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
