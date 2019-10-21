---
title: Доступ к веб-службам приложения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
ms.openlocfilehash: faefb49e252445216bdce2e5606b1eb3fbcd430d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582010"
---
# <a name="accessing-application-web-services-visual-basic"></a><span data-ttu-id="4a071-102">Доступ к веб-службам приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a071-102">Accessing Application Web Services (Visual Basic)</span></span>

<span data-ttu-id="4a071-103">Объект `My.WebServices` предоставляет экземпляр каждой веб-службы, на которую ссылается текущий проект.</span><span class="sxs-lookup"><span data-stu-id="4a071-103">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="4a071-104">Каждый экземпляр создается по запросу.</span><span class="sxs-lookup"><span data-stu-id="4a071-104">Each instance is instantiated on demand.</span></span> <span data-ttu-id="4a071-105">Доступ к этим веб-службам можно получить через свойства объекта `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="4a071-105">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="4a071-106">Имя свойства совпадает с именем веб-службы, к которой обращается свойство.</span><span class="sxs-lookup"><span data-stu-id="4a071-106">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="4a071-107">Любой класс, наследуемый от <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>, является веб-службой.</span><span class="sxs-lookup"><span data-stu-id="4a071-107">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span>

## <a name="tasks"></a><span data-ttu-id="4a071-108">Задачи</span><span class="sxs-lookup"><span data-stu-id="4a071-108">Tasks</span></span>

<span data-ttu-id="4a071-109">В следующей таблице перечислены возможные способы доступа к веб-службам, на которые ссылается приложение.</span><span class="sxs-lookup"><span data-stu-id="4a071-109">The following table lists possible ways to access Web services referenced by an application.</span></span>

|<span data-ttu-id="4a071-110">Кому</span><span class="sxs-lookup"><span data-stu-id="4a071-110">To</span></span>|<span data-ttu-id="4a071-111">См.</span><span class="sxs-lookup"><span data-stu-id="4a071-111">See</span></span>|
|---|---|
|<span data-ttu-id="4a071-112">Вызов веб-службы</span><span class="sxs-lookup"><span data-stu-id="4a071-112">Call a Web service</span></span>|[<span data-ttu-id="4a071-113">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="4a071-113">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)|
|<span data-ttu-id="4a071-114">Вызов веб-службы в асинхронном режиме и обработка события при его завершении</span><span class="sxs-lookup"><span data-stu-id="4a071-114">Call a Web service asynchronously and handle an event when it completes</span></span>|[<span data-ttu-id="4a071-115">Практическое руководство. Асинхронный вызов веб-службы</span><span class="sxs-lookup"><span data-stu-id="4a071-115">How to: Call a Web Service Asynchronously</span></span>](../../../visual-basic/developing-apps/programming/how-to-call-a-web-service-asynchronously.md)|

## <a name="see-also"></a><span data-ttu-id="4a071-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4a071-116">See also</span></span>

- [<span data-ttu-id="4a071-117">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="4a071-117">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
