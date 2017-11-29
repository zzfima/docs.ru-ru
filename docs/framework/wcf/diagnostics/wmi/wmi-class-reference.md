---
title: "Справочные сведения по классам WMI"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ee03f0c567f2b154eaf2e7fdf608b093cfbe2d1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="wmi-class-reference"></a><span data-ttu-id="f21c1-102">Справочные сведения по классам WMI</span><span class="sxs-lookup"><span data-stu-id="f21c1-102">WMI Class Reference</span></span>
<span data-ttu-id="f21c1-103">В данном разделе перечислены все классы WMI, представленные поставщиком WMI [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f21c1-103">This section lists all the WMI classes exposed by the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] WMI provider.</span></span>  
  
## <a name="accessing-wmi-instances"></a><span data-ttu-id="f21c1-104">Доступ к экземплярам WMI</span><span class="sxs-lookup"><span data-stu-id="f21c1-104">Accessing WMI Instances</span></span>  
 <span data-ttu-id="f21c1-105">Все классы, перечисленные в ссылках на объект WMI, невозможно создать напрямую, за исключением классов службы, домена приложения, контракта, ServiceToEndpointAssociation и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f21c1-105">All the classes listed in the WMI Object Reference cannot be directly instantiated, except for Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation and Endpoint.</span></span> <span data-ttu-id="f21c1-106">Чтобы получить доступ к другим экземплярам, можно получить доступ к свойствам указанных выше классов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="f21c1-106">To access other instances, you can access the properties of the previously mentioned top level classes.</span></span> <span data-ttu-id="f21c1-107">Например, доступ к экземпляру TransportBindingElement можно получить следующим образом: экземпляр класса конечной точки -> привязка -> класс BindingElements.</span><span class="sxs-lookup"><span data-stu-id="f21c1-107">For example, you can access the TransportBindingElement instance from the Endpoint instance -> Binding -> BindingElements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f21c1-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="f21c1-108">In This Section</span></span>  
 [<span data-ttu-id="f21c1-109">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="f21c1-109">ActivityTransfer</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/activitytransfer.md)  
  
 [<span data-ttu-id="f21c1-110">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="f21c1-110">AppDomainInfo</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md)  
  
 [<span data-ttu-id="f21c1-111">AspNetCompatibilityRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="f21c1-111">AspNetCompatibilityRequirementsAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/aspnetcompatibilityrequirementsattribute.md)  
  
 [<span data-ttu-id="f21c1-112">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-112">AsymmetricSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/asymmetricsecuritybindingelement.md)  
  
 <span data-ttu-id="f21c1-113">«Класс поведение»</span><span class="sxs-lookup"><span data-stu-id="f21c1-113">"Behavior class"</span></span>  
  
 [<span data-ttu-id="f21c1-114">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-114">BinaryMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/binarymessageencodingbindingelement.md)  
  
 [<span data-ttu-id="f21c1-115">Привязки</span><span class="sxs-lookup"><span data-stu-id="f21c1-115">Binding</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/binding.md)  
  
 [<span data-ttu-id="f21c1-116">BindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-116">BindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/bindingelement.md)  
  
 [<span data-ttu-id="f21c1-117">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-117">CallbackBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/callbackbehavior.md)  
  
 [<span data-ttu-id="f21c1-118">Класс Channel</span><span class="sxs-lookup"><span data-stu-id="f21c1-118">Channel class</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/channel-class.md)  
  
 [<span data-ttu-id="f21c1-119">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f21c1-119">ChannelPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/channelpoolsettings.md)  
  
 [<span data-ttu-id="f21c1-120">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="f21c1-120">ClientCredentials</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/clientcredentials.md)  
  
 [<span data-ttu-id="f21c1-121">ClientViaBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-121">ClientViaBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md)  
  
 [<span data-ttu-id="f21c1-122">CompositeDuplexBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-122">CompositeDuplexBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/compositeduplexbindingelement.md)  
  
 [<span data-ttu-id="f21c1-123">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-123">ConnectionOrientedTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/connectionorientedtransportbindingelement.md)  
  
 [<span data-ttu-id="f21c1-124">Контракт</span><span class="sxs-lookup"><span data-stu-id="f21c1-124">Contract</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/contract.md)  
  
 [<span data-ttu-id="f21c1-125">CustomBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-125">CustomBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/custombindingelement.md)  
  
 [<span data-ttu-id="f21c1-126">Атрибут DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="f21c1-126">DeliveryRequirementsAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/deliveryrequirementsattribute.md)  
  
 [<span data-ttu-id="f21c1-127">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="f21c1-127">Endpoint</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md)  
  
 [<span data-ttu-id="f21c1-128">HttpsTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-128">HttpsTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/httpstransportbindingelement.md)  
  
 [<span data-ttu-id="f21c1-129">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-129">HttpTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/httptransportbindingelement.md)  
  
 [<span data-ttu-id="f21c1-130">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f21c1-130">LocalServiceSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/localservicesecuritysettings.md)  
  
 [<span data-ttu-id="f21c1-131">Matchallendpointbehavior наследуется</span><span class="sxs-lookup"><span data-stu-id="f21c1-131">MatchAllEndpointBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/matchallendpointbehavior.md)  
  
 [<span data-ttu-id="f21c1-132">MessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-132">MessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/messageencodingbindingelement.md)  
  
 [<span data-ttu-id="f21c1-133">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="f21c1-133">MsmqBindingElementBase</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqbindingelementbase.md)  
  
 [<span data-ttu-id="f21c1-134">MsmqIntegrationBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-134">MsmqIntegrationBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqintegrationbindingelement.md)  
  
 [<span data-ttu-id="f21c1-135">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-135">MsmqTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqtransportbindingelement.md)  
  
 [<span data-ttu-id="f21c1-136">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-136">MtomMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/mtommessageencodingbindingelement.md)  
  
 [<span data-ttu-id="f21c1-137">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-137">MustUnderstandBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/mustunderstandbehavior.md)  
  
 [<span data-ttu-id="f21c1-138">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f21c1-138">NamedPipeConnectionPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipeconnectionpoolsettings.md)  
  
 [<span data-ttu-id="f21c1-139">NamedPipeTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-139">NamedPipeTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipetransportbindingelement.md)  
  
 [<span data-ttu-id="f21c1-140">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-140">OneWayBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/onewaybindingelement.md)  
  
 <span data-ttu-id="f21c1-141">«Класс операции»</span><span class="sxs-lookup"><span data-stu-id="f21c1-141">"Operation class"</span></span>  
  
 [<span data-ttu-id="f21c1-142">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="f21c1-142">OperationBehaviorAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/operationbehaviorattribute.md)  
  
 [<span data-ttu-id="f21c1-143">PeerCustomResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-143">PeerCustomResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peercustomresolverbindingelement.md)  
  
 [<span data-ttu-id="f21c1-144">PeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-144">PeerResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peerresolverbindingelement.md)  
  
 [<span data-ttu-id="f21c1-145">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f21c1-145">PeerSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peersecuritysettings.md)  
  
 [<span data-ttu-id="f21c1-146">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-146">PeerTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportbindingelement.md)  
  
 [<span data-ttu-id="f21c1-147">PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f21c1-147">PeerTransportSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportsecuritysettings.md)  
  
 [<span data-ttu-id="f21c1-148">PnrpPeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-148">PnrpPeerResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/pnrppeerresolverbindingelement.md)  
  
 [<span data-ttu-id="f21c1-149">PrivacyNoticeBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-149">PrivacyNoticeBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/privacynoticebindingelement.md)  
  
 [<span data-ttu-id="f21c1-150">Элемент ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-150">ReliableSessionBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/reliablesessionbindingelement.md)  
  
 [<span data-ttu-id="f21c1-151">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-151">SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md)  
  
 [<span data-ttu-id="f21c1-152">Службы</span><span class="sxs-lookup"><span data-stu-id="f21c1-152">Service</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/service.md)  
  
 [<span data-ttu-id="f21c1-153">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="f21c1-153">ServiceAppDomain</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/serviceappdomain.md)  
  
 [<span data-ttu-id="f21c1-154">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-154">ServiceAuthorizationBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/serviceauthorizationbehavior.md)  
  
 [<span data-ttu-id="f21c1-155">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="f21c1-155">ServiceBehaviorAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicebehaviorattribute.md)  
  
 [<span data-ttu-id="f21c1-156">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="f21c1-156">ServiceCredentials</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicecredentials.md)  
  
 [<span data-ttu-id="f21c1-157">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-157">ServiceDebugBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicedebugbehavior.md)  
  
 [<span data-ttu-id="f21c1-158">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-158">ServiceMetadataBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicemetadatabehavior.md)  
  
 [<span data-ttu-id="f21c1-159">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-159">ServiceSecurityAuditBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicesecurityauditbehavior.md)  
  
 [<span data-ttu-id="f21c1-160">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-160">ServiceThrottlingBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicethrottlingbehavior.md)  
  
 [<span data-ttu-id="f21c1-161">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-161">ServiceTimeoutsBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicetimeoutsbehavior.md)  
  
 [<span data-ttu-id="f21c1-162">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="f21c1-162">ServiceToEndpointAssociation</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicetoendpointassociation.md)  
  
 [<span data-ttu-id="f21c1-163">SslStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-163">SslStreamSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/sslstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="f21c1-164">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-164">SymmetricSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)  
  
 [<span data-ttu-id="f21c1-165">Synchronousreceivebehavior наследуется</span><span class="sxs-lookup"><span data-stu-id="f21c1-165">SynchronousReceiveBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/synchronousreceivebehavior.md)  
  
 [<span data-ttu-id="f21c1-166">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f21c1-166">TcpConnectionPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tcpconnectionpoolsettings.md)  
  
 [<span data-ttu-id="f21c1-167">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-167">TcpTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tcptransportbindingelement.md)  
  
 [<span data-ttu-id="f21c1-168">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-168">TextMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/textmessageencodingbindingelement.md)  
  
 [<span data-ttu-id="f21c1-169">Прослушиватель трассировки</span><span class="sxs-lookup"><span data-stu-id="f21c1-169">TraceListener</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistener.md)  
  
 [<span data-ttu-id="f21c1-170">TraceListenerArgument</span><span class="sxs-lookup"><span data-stu-id="f21c1-170">TraceListenerArgument</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistenerargument.md)  
  
 [<span data-ttu-id="f21c1-171">TransactedBatchingBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-171">TransactedBatchingBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactedbatchingbehavior.md)  
  
 [<span data-ttu-id="f21c1-172">TransactionFlowAttribute</span><span class="sxs-lookup"><span data-stu-id="f21c1-172">TransactionFlowAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowattribute.md)  
  
 [<span data-ttu-id="f21c1-173">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-173">TransactionFlowBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowbindingelement.md)  
  
 [<span data-ttu-id="f21c1-174">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-174">TransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transportbindingelement.md)  
  
 [<span data-ttu-id="f21c1-175">TransportSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-175">TransportSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transportsecuritybindingelement.md)  
  
 [<span data-ttu-id="f21c1-176">UseManagedPresentationBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-176">UseManagedPresentationBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/usemanagedpresentationbindingelement.md)  
  
 [<span data-ttu-id="f21c1-177">WindowsStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f21c1-177">WindowsStreamSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/windowsstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="f21c1-178">WSAT_TraceEvent</span><span class="sxs-lookup"><span data-stu-id="f21c1-178">WSAT_TraceEvent</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceevent.md)  
  
 [<span data-ttu-id="f21c1-179">WSAT_TraceProvider</span><span class="sxs-lookup"><span data-stu-id="f21c1-179">WSAT_TraceProvider</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceprovider.md)  
  
 [<span data-ttu-id="f21c1-180">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="f21c1-180">WSAT_TraceRecord</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-tracerecord.md)  
  
 [<span data-ttu-id="f21c1-181">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="f21c1-181">XmlDictionaryReaderQuotas</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/xmldictionaryreaderquotas.md)  
  
 [<span data-ttu-id="f21c1-182">XmlSerializerOperationBehavior</span><span class="sxs-lookup"><span data-stu-id="f21c1-182">XmlSerializerOperationBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/xmlserializeroperationbehavior.md)
