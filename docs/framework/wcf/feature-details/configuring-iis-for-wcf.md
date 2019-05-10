---
title: Настройка IIS 7.0 для Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 6962ed1dccca6db2e55554459742adab210585ef
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64654996"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a><span data-ttu-id="d73a7-102">Настройка IIS 7.0 для Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d73a7-102">Configuring Internet Information Services 7.0 for Windows Communication Foundation</span></span>

<span data-ttu-id="d73a7-103">Службы IIS 7.0 имеют модульную архитектуру, что позволяет выборочно устанавливать необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="d73a7-103">Internet Information Services (IIS) 7.0 has a modular design that allows you to selectively install components that are required.</span></span> <span data-ttu-id="d73a7-104">Эта архитектура основана на построенной на базе манифестов технологии разбиения на компоненты, появившейся в [!INCLUDE[wv](../../../../includes/wv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d73a7-104">This design is based on the new manifest-driven componentization technology introduced in [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span> <span data-ttu-id="d73a7-105">Существует более чем из 40 отдельных функциональных компонентов IIS 7.0, которая может устанавливаться независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="d73a7-105">There are more than 40 standalone feature components of IIS 7.0 that can be installed independently.</span></span> <span data-ttu-id="d73a7-106">Это позволяет ИТ-специалистам легко настраивать службы в соответствии с конкретными требованиями.</span><span class="sxs-lookup"><span data-stu-id="d73a7-106">This allows IT professionals to easily customize the installation as required.</span></span> <span data-ttu-id="d73a7-107">В этом разделе описывается настройка IIS 7.0 для использования с Windows Communication Foundation (WCF) и определить, какие компоненты являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="d73a7-107">This topic discusses how to configure IIS 7.0 for use with Windows Communication Foundation (WCF) and determine which components are required.</span></span>

## <a name="minimal-installation-installing-was"></a><span data-ttu-id="d73a7-108">Минимальная установка: Установка службы WAS</span><span class="sxs-lookup"><span data-stu-id="d73a7-108">Minimal Installation: Installing WAS</span></span>
 <span data-ttu-id="d73a7-109">Минимальная установка всего пакета IIS 7.0 — установить службу активации процессов Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="d73a7-109">The minimal installation of the whole IIS 7.0 package is to install the Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="d73a7-110">Это независимый компонент и это единственный компонент с помощью IIS 7.0, которая доступна для всех [!INCLUDE[wv](../../../../includes/wv-md.md)] операционных систем (Home Basic, Home Premium, Business и Ultimate и Enterprise).</span><span class="sxs-lookup"><span data-stu-id="d73a7-110">WAS is a standalone feature and it is the only feature from the IIS 7.0 that is available for all [!INCLUDE[wv](../../../../includes/wv-md.md)] operating systems (Home Basic, Home Premium, Business, and Ultimate and Enterprise).</span></span>

 <span data-ttu-id="d73a7-111">С помощью панели управления щелкните **программы** и нажмите кнопку **или отключение компонентов Windows включить** в категории **программы и компоненты**, компоненты WAS появится в список, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="d73a7-111">From the Control Panel, click **Programs** and then click **Turn Windows features on or off** which is listed under **Programs and Features**, the WAS component is shown in the list as in the following illustration.</span></span>

 <span data-ttu-id="d73a7-112">![Включение функции или отключить диалоговое окно](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span><span class="sxs-lookup"><span data-stu-id="d73a7-112">![Turn Features On or Off Dialog](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span></span>

 <span data-ttu-id="d73a7-113">Этот компонент включает следующие подкомпоненты:</span><span class="sxs-lookup"><span data-stu-id="d73a7-113">This feature has the following sub-components:</span></span>

- <span data-ttu-id="d73a7-114">Среда .NET Environment</span><span class="sxs-lookup"><span data-stu-id="d73a7-114">.NET Environment</span></span>

- <span data-ttu-id="d73a7-115">Интерфейсы API настройки</span><span class="sxs-lookup"><span data-stu-id="d73a7-115">Configuration APIs</span></span>

- <span data-ttu-id="d73a7-116">Модель процессов</span><span class="sxs-lookup"><span data-stu-id="d73a7-116">Process Model</span></span>

 <span data-ttu-id="d73a7-117">Если вы выберите корневой узел WAS, только **модель процесса** будет выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d73a7-117">If you select the root node of WAS, only the **Process Model** sub-node is checked by default.</span></span> <span data-ttu-id="d73a7-118">Обратите внимание, что при такой установке устанавливается только служба WAS, поскольку поддержка веб-сервера отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d73a7-118">Please note that with this installation you are only installing WAS, because there is no support for a Web server.</span></span>

 <span data-ttu-id="d73a7-119">Чтобы обеспечить WCF или какой-либо работы приложения ASP.NET, проверьте **среды .NET** флажок.</span><span class="sxs-lookup"><span data-stu-id="d73a7-119">To make WCF or any ASP.NET application work, check the **.NET Environment** checkbox.</span></span> <span data-ttu-id="d73a7-120">Это означает, что все компоненты WAS требуются WCF и ASP.NET, хорошо работать.</span><span class="sxs-lookup"><span data-stu-id="d73a7-120">This means that all of WAS components are required to make WCF and ASP.NET to work well.</span></span> <span data-ttu-id="d73a7-121">Они автоматически выбираются при установке какого либо из этих компонентов.</span><span class="sxs-lookup"><span data-stu-id="d73a7-121">These are automatically checked once you install any of those components.</span></span>

## <a name="iis-70-default-installation"></a><span data-ttu-id="d73a7-122">IIS 7.0: Установка по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d73a7-122">IIS 7.0: Default Installation</span></span>
 <span data-ttu-id="d73a7-123">Проверив **Internet Information Services** компонентов, некоторые подкомпоненты проверяются автоматически, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="d73a7-123">By checking the **Internet Information Services** feature, some of the sub-nodes are automatically checked as shown in the following illustration.</span></span>

 <span data-ttu-id="d73a7-124">![Параметры по умолчанию для компонентов IIS 7.0](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span><span class="sxs-lookup"><span data-stu-id="d73a7-124">![Default settings for IIS 7.0 features](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span></span>

 <span data-ttu-id="d73a7-125">Это установка по умолчанию службы IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="d73a7-125">This is the default installation of IIS 7.0.</span></span> <span data-ttu-id="d73a7-126">При такой установке IIS 7.0 можно использовать для статического содержимого службы (например, HTML-страниц и другим содержимым).</span><span class="sxs-lookup"><span data-stu-id="d73a7-126">With this installation, you can use IIS 7.0 to service static content (such as HTML pages and other content).</span></span> <span data-ttu-id="d73a7-127">Тем не менее нельзя запускать приложения ASP.NET или CGI или размещать службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d73a7-127">However, you cannot run ASP.NET or CGI applications or host WCF services.</span></span>

## <a name="iis-70-installation-with-aspnet-support"></a><span data-ttu-id="d73a7-128">IIS 7.0: Установка с поддержкой ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d73a7-128">IIS 7.0: Installation with ASP.NET Support</span></span>
 <span data-ttu-id="d73a7-129">Необходимо установить ASP.NET, чтобы работать на IIS 7.0 ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d73a7-129">You must install ASP.NET to make ASP.NET work on IIS 7.0.</span></span> <span data-ttu-id="d73a7-130">После проверки **ASP.NET**, экран должен выглядеть как на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="d73a7-130">After checking **ASP.NET**, your screen should look like the following illustration.</span></span>

 <span data-ttu-id="d73a7-131">![Asp.NET обязательные параметры](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span><span class="sxs-lookup"><span data-stu-id="d73a7-131">![Asp.NET required settings](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span></span>

 <span data-ttu-id="d73a7-132">Это минимальную среду для приложений WCF и ASP.NET в IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="d73a7-132">This is the minimal environment for both WCF and ASP.NET applications to work in IIS 7.0.</span></span>

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a><span data-ttu-id="d73a7-133">IIS 7.0: Компоненты IIS 6.0 совместимости</span><span class="sxs-lookup"><span data-stu-id="d73a7-133">IIS 7.0: Installation with IIS 6.0 Compatibility Components</span></span>
 <span data-ttu-id="d73a7-134">При установке IIS 7.0 в системе с Visual Studio 2005 или некоторые другие сценарии автоматизации или инструменты (например, Adsutil.vbs), которые настраивают виртуальные приложения, использующие API метабазы IIS 6.0, убедитесь, что установлен флажок IIS 6.0 **средств работы со сценариями**.</span><span class="sxs-lookup"><span data-stu-id="d73a7-134">When installing IIS 7.0 on a system with Visual Studio 2005 or some other automation scripts or tools (such as Adsutil.vbs) that configure virtual applications that use IIS 6.0 Metabase API, ensure that you check the IIS 6.0 **Scripting Tools**.</span></span> <span data-ttu-id="d73a7-135">При этом автоматически проверяется другие компоненты узла IIS 6.0 **совместимость управления**.</span><span class="sxs-lookup"><span data-stu-id="d73a7-135">This automatically checks the other sub-nodes of IIS 6.0 **Management Compatibility**.</span></span> <span data-ttu-id="d73a7-136">На следующем рисунке показан экран, после этого:</span><span class="sxs-lookup"><span data-stu-id="d73a7-136">The following illustration shows the screen after this is done:</span></span>

 <span data-ttu-id="d73a7-137">![Параметры совместимости служб IIS 6.0 управления](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span><span class="sxs-lookup"><span data-stu-id="d73a7-137">![IIS 6.0 Management Compatibility Settings](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span></span>

 <span data-ttu-id="d73a7-138">При такой установке имеется все необходимое для использования функций IIS 7.0, ASP.NET и WCF и примеры, доступные в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d73a7-138">With this installation, you have everything required to use IIS 7.0, ASP.NET and WCF features and samples available on the Web.</span></span>

## <a name="request-limits"></a><span data-ttu-id="d73a7-139">Ограничения запросов</span><span class="sxs-lookup"><span data-stu-id="d73a7-139">Request Limits</span></span>
 <span data-ttu-id="d73a7-140">В [!INCLUDE[wv](../../../../includes/wv-md.md)] со службами IIS 7 были изменены значения по умолчанию для параметров `maxUri` и `maxQueryStringSize`.</span><span class="sxs-lookup"><span data-stu-id="d73a7-140">On [!INCLUDE[wv](../../../../includes/wv-md.md)] with IIS 7 the default value of the `maxUri` and `maxQueryStringSize` settings have been changed.</span></span> <span data-ttu-id="d73a7-141">По умолчанию фильтрация запросов в IIS 7.0 допускает использование URL-адресов длиной 4096 знаков и строк запросов длиной 2048 знаков.</span><span class="sxs-lookup"><span data-stu-id="d73a7-141">By default, request filtering in IIS 7.0 allows a URL length of 4096 characters and a query string length of 2048 characters.</span></span> <span data-ttu-id="d73a7-142">Чтобы изменить эти значения по умолчанию, добавьте в файл App.config следующий XML-код.</span><span class="sxs-lookup"><span data-stu-id="d73a7-142">To change these defaults add the following XML to your App.config file.</span></span>

```xml
 <system.webServer>
    <security>
        <requestFiltering>
            <requestLimits maxUrl="8192" maxQueryString="8192" />
        </requestFiltering>
    </security>
 </system.webServer>
 ```

## <a name="see-also"></a><span data-ttu-id="d73a7-143">См. также</span><span class="sxs-lookup"><span data-stu-id="d73a7-143">See also</span></span>

- [<span data-ttu-id="d73a7-144">Архитектура активации WAS</span><span class="sxs-lookup"><span data-stu-id="d73a7-144">WAS Activation Architecture</span></span>](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [<span data-ttu-id="d73a7-145">Настройка WAS для использования с WCF</span><span class="sxs-lookup"><span data-stu-id="d73a7-145">Configuring WAS for Use with WCF</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [<span data-ttu-id="d73a7-146">Практическое руководство. Установка и настройка компонентов активации WCF</span><span class="sxs-lookup"><span data-stu-id="d73a7-146">How to: Install and Configure WCF Activation Components</span></span>](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [<span data-ttu-id="d73a7-147">Функции размещения Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="d73a7-147">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
