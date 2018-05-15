---
title: Справочные сведения по классам WMI
ms.date: 03/30/2017
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
ms.openlocfilehash: 73b36bfc3df917982a2cc9071bdb31f42b3b2dff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="wmi-class-reference"></a><span data-ttu-id="d5e2b-102">Справочные сведения по классам WMI</span><span class="sxs-lookup"><span data-stu-id="d5e2b-102">WMI Class Reference</span></span>
<span data-ttu-id="d5e2b-103">В этом разделе перечислены все классы WMI, представленные поставщиком WMI Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d5e2b-103">This section lists all the WMI classes exposed by the Windows Communication Foundation (WCF) WMI provider.</span></span>  
  
## <a name="accessing-wmi-instances"></a><span data-ttu-id="d5e2b-104">Доступ к экземплярам WMI</span><span class="sxs-lookup"><span data-stu-id="d5e2b-104">Accessing WMI Instances</span></span>  
 <span data-ttu-id="d5e2b-105">Все классы, перечисленные в ссылках на объект WMI, невозможно создать напрямую, за исключением классов службы, домена приложения, контракта, ServiceToEndpointAssociation и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d5e2b-105">All the classes listed in the WMI Object Reference cannot be directly instantiated, except for Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation and Endpoint.</span></span> <span data-ttu-id="d5e2b-106">Чтобы получить доступ к другим экземплярам, можно получить доступ к свойствам указанных выше классов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="d5e2b-106">To access other instances, you can access the properties of the previously mentioned top level classes.</span></span> <span data-ttu-id="d5e2b-107">Например, доступ к экземпляру TransportBindingElement можно получить следующим образом: экземпляр класса конечной точки -> привязка -> класс BindingElements.</span><span class="sxs-lookup"><span data-stu-id="d5e2b-107">For example, you can access the TransportBindingElement instance from the Endpoint instance -> Binding -> BindingElements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5e2b-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d5e2b-108">In This Section</span></span>  
 [<span data-ttu-id="d5e2b-109">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="d5e2b-109">ActivityTransfer</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/activitytransfer.md)  
  
 [<span data-ttu-id="d5e2b-110">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="d5e2b-110">AppDomainInfo</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md)  
  
 [<span data-ttu-id="d5e2b-111">AspNetCompatibilityRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="d5e2b-111">AspNetCompatibilityRequirementsAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/aspnetcompatibilityrequirementsattribute.md)  
  
 [<span data-ttu-id="d5e2b-112">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-112">AsymmetricSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/asymmetricsecuritybindingelement.md)  
  
 <span data-ttu-id="d5e2b-113">«Класс поведение»</span><span class="sxs-lookup"><span data-stu-id="d5e2b-113">"Behavior class"</span></span>  
  
 [<span data-ttu-id="d5e2b-114">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-114">BinaryMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/binarymessageencodingbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-115">Binding</span><span class="sxs-lookup"><span data-stu-id="d5e2b-115">Binding</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/binding.md)  
  
 [<span data-ttu-id="d5e2b-116">BindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-116">BindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/bindingelement.md)  
  
 [<span data-ttu-id="d5e2b-117">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-117">CallbackBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/callbackbehavior.md)  
  
 [<span data-ttu-id="d5e2b-118">Класс Channel</span><span class="sxs-lookup"><span data-stu-id="d5e2b-118">Channel class</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/channel-class.md)  
  
 [<span data-ttu-id="d5e2b-119">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d5e2b-119">ChannelPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/channelpoolsettings.md)  
  
 [<span data-ttu-id="d5e2b-120">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="d5e2b-120">ClientCredentials</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/clientcredentials.md)  
  
 [<span data-ttu-id="d5e2b-121">ClientViaBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-121">ClientViaBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md)  
  
 [<span data-ttu-id="d5e2b-122">CompositeDuplexBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-122">CompositeDuplexBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/compositeduplexbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-123">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-123">ConnectionOrientedTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/connectionorientedtransportbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-124">Contract</span><span class="sxs-lookup"><span data-stu-id="d5e2b-124">Contract</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/contract.md)  
  
 [<span data-ttu-id="d5e2b-125">CustomBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-125">CustomBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/custombindingelement.md)  
  
 [<span data-ttu-id="d5e2b-126">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="d5e2b-126">DeliveryRequirementsAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/deliveryrequirementsattribute.md)  
  
 [<span data-ttu-id="d5e2b-127">Endpoint</span><span class="sxs-lookup"><span data-stu-id="d5e2b-127">Endpoint</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md)  
  
 [<span data-ttu-id="d5e2b-128">HttpsTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-128">HttpsTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/httpstransportbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-129">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-129">HttpTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/httptransportbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-130">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d5e2b-130">LocalServiceSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/localservicesecuritysettings.md)  
  
 [<span data-ttu-id="d5e2b-131">MatchAllEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-131">MatchAllEndpointBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/matchallendpointbehavior.md)  
  
 [<span data-ttu-id="d5e2b-132">MessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-132">MessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/messageencodingbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-133">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="d5e2b-133">MsmqBindingElementBase</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqbindingelementbase.md)  
  
 [<span data-ttu-id="d5e2b-134">MsmqIntegrationBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-134">MsmqIntegrationBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqintegrationbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-135">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-135">MsmqTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqtransportbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-136">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-136">MtomMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/mtommessageencodingbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-137">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-137">MustUnderstandBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/mustunderstandbehavior.md)  
  
 [<span data-ttu-id="d5e2b-138">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d5e2b-138">NamedPipeConnectionPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipeconnectionpoolsettings.md)  
  
 [<span data-ttu-id="d5e2b-139">NamedPipeTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-139">NamedPipeTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipetransportbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-140">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-140">OneWayBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/onewaybindingelement.md)  
  
 <span data-ttu-id="d5e2b-141">«Класс операции»</span><span class="sxs-lookup"><span data-stu-id="d5e2b-141">"Operation class"</span></span>  
  
 [<span data-ttu-id="d5e2b-142">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="d5e2b-142">OperationBehaviorAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/operationbehaviorattribute.md)  
  
 [<span data-ttu-id="d5e2b-143">PeerCustomResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-143">PeerCustomResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peercustomresolverbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-144">PeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-144">PeerResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peerresolverbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-145">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d5e2b-145">PeerSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peersecuritysettings.md)  
  
 [<span data-ttu-id="d5e2b-146">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-146">PeerTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-147">PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d5e2b-147">PeerTransportSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportsecuritysettings.md)  
  
 [<span data-ttu-id="d5e2b-148">PnrpPeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-148">PnrpPeerResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/pnrppeerresolverbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-149">PrivacyNoticeBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-149">PrivacyNoticeBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/privacynoticebindingelement.md)  
  
 [<span data-ttu-id="d5e2b-150">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-150">ReliableSessionBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/reliablesessionbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-151">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-151">SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md)  
  
 [<span data-ttu-id="d5e2b-152">Service</span><span class="sxs-lookup"><span data-stu-id="d5e2b-152">Service</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/service.md)  
  
 [<span data-ttu-id="d5e2b-153">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="d5e2b-153">ServiceAppDomain</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/serviceappdomain.md)  
  
 [<span data-ttu-id="d5e2b-154">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-154">ServiceAuthorizationBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/serviceauthorizationbehavior.md)  
  
 [<span data-ttu-id="d5e2b-155">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="d5e2b-155">ServiceBehaviorAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicebehaviorattribute.md)  
  
 [<span data-ttu-id="d5e2b-156">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="d5e2b-156">ServiceCredentials</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicecredentials.md)  
  
 [<span data-ttu-id="d5e2b-157">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-157">ServiceDebugBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicedebugbehavior.md)  
  
 [<span data-ttu-id="d5e2b-158">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-158">ServiceMetadataBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicemetadatabehavior.md)  
  
 [<span data-ttu-id="d5e2b-159">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-159">ServiceSecurityAuditBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicesecurityauditbehavior.md)  
  
 [<span data-ttu-id="d5e2b-160">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-160">ServiceThrottlingBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicethrottlingbehavior.md)  
  
 [<span data-ttu-id="d5e2b-161">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-161">ServiceTimeoutsBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicetimeoutsbehavior.md)  
  
 [<span data-ttu-id="d5e2b-162">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="d5e2b-162">ServiceToEndpointAssociation</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicetoendpointassociation.md)  
  
 [<span data-ttu-id="d5e2b-163">SslStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-163">SslStreamSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/sslstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="d5e2b-164">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-164">SymmetricSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)  
  
 [<span data-ttu-id="d5e2b-165">SynchronousReceiveBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-165">SynchronousReceiveBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/synchronousreceivebehavior.md)  
  
 [<span data-ttu-id="d5e2b-166">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d5e2b-166">TcpConnectionPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tcpconnectionpoolsettings.md)  
  
 [<span data-ttu-id="d5e2b-167">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-167">TcpTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tcptransportbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-168">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-168">TextMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/textmessageencodingbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-169">TraceListener</span><span class="sxs-lookup"><span data-stu-id="d5e2b-169">TraceListener</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistener.md)  
  
 [<span data-ttu-id="d5e2b-170">TraceListenerArgument</span><span class="sxs-lookup"><span data-stu-id="d5e2b-170">TraceListenerArgument</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistenerargument.md)  
  
 [<span data-ttu-id="d5e2b-171">TransactedBatchingBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-171">TransactedBatchingBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactedbatchingbehavior.md)  
  
 [<span data-ttu-id="d5e2b-172">TransactionFlowAttribute</span><span class="sxs-lookup"><span data-stu-id="d5e2b-172">TransactionFlowAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowattribute.md)  
  
 [<span data-ttu-id="d5e2b-173">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-173">TransactionFlowBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-174">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-174">TransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transportbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-175">TransportSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-175">TransportSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transportsecuritybindingelement.md)  
  
 [<span data-ttu-id="d5e2b-176">UseManagedPresentationBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-176">UseManagedPresentationBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/usemanagedpresentationbindingelement.md)  
  
 [<span data-ttu-id="d5e2b-177">WindowsStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d5e2b-177">WindowsStreamSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/windowsstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="d5e2b-178">WSAT_TraceEvent</span><span class="sxs-lookup"><span data-stu-id="d5e2b-178">WSAT_TraceEvent</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceevent.md)  
  
 [<span data-ttu-id="d5e2b-179">WSAT_TraceProvider</span><span class="sxs-lookup"><span data-stu-id="d5e2b-179">WSAT_TraceProvider</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceprovider.md)  
  
 [<span data-ttu-id="d5e2b-180">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="d5e2b-180">WSAT_TraceRecord</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-tracerecord.md)  
  
 [<span data-ttu-id="d5e2b-181">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d5e2b-181">XmlDictionaryReaderQuotas</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/xmldictionaryreaderquotas.md)  
  
 [<span data-ttu-id="d5e2b-182">XmlSerializerOperationBehavior</span><span class="sxs-lookup"><span data-stu-id="d5e2b-182">XmlSerializerOperationBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/xmlserializeroperationbehavior.md)
