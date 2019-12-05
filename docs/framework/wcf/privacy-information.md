---
title: Сведения о политике конфиденциальности Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: c5500b8fd8b35081e83e2e9279dc4f236ef3c7b0
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837939"
---
# <a name="windows-communication-foundation-privacy-information"></a><span data-ttu-id="38f54-102">Сведения о политике конфиденциальности Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="38f54-102">Windows Communication Foundation Privacy Information</span></span>
<span data-ttu-id="38f54-103">Корпорация Майкрософт стремится защитить конфиденциальные данные конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="38f54-103">Microsoft is committed to protecting end-users' privacy.</span></span> <span data-ttu-id="38f54-104">При создании приложения с помощью Windows Communication Foundation (WCF) версии 3,0 приложение может повлиять на конфиденциальность конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="38f54-104">When you build an application using Windows Communication Foundation (WCF), version 3.0, your application may impact your end-users' privacy.</span></span> <span data-ttu-id="38f54-105">Например, приложение может явным образом собирать контактные данные пользователей или запрашивать/отправлять информацию через Интернет на свой веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="38f54-105">For example, your application may explicitly collect user contact information, or it may request or send information over the Internet to your Web site.</span></span> <span data-ttu-id="38f54-106">Если в приложение внедряется технология Майкрософт, у этой технологии может быть свое поведение, которое способно повлиять на конфиденциальность данных приложения.</span><span class="sxs-lookup"><span data-stu-id="38f54-106">If you embed Microsoft technology in your application, that technology may have its own behavior that might affect privacy.</span></span> <span data-ttu-id="38f54-107">WCF не отправляет сведения в корпорацию Майкрософт из вашего приложения, если вы или конечный пользователь не отправите его нам.</span><span class="sxs-lookup"><span data-stu-id="38f54-107">WCF does not send any information to Microsoft from your application unless you or the end-user choose to send it to us.</span></span>  
  
## <a name="wcf-in-brief"></a><span data-ttu-id="38f54-108">Вкратце о WCF</span><span class="sxs-lookup"><span data-stu-id="38f54-108">WCF in Brief</span></span>  
 <span data-ttu-id="38f54-109">WCF — это распределенная платформа обмена сообщениями, использующая платформу Microsoft .NET, которая позволяет разработчикам создавать распределенные приложения.</span><span class="sxs-lookup"><span data-stu-id="38f54-109">WCF is a distributed messaging framework using the Microsoft .NET Framework that allows developers to build distributed applications.</span></span> <span data-ttu-id="38f54-110">Сообщения, обмен которыми осуществляется между двумя приложениями, содержат информацию заголовка и тела сообщения.</span><span class="sxs-lookup"><span data-stu-id="38f54-110">Messages communicated between two applications contain header and body information.</span></span>  
  
 <span data-ttu-id="38f54-111">Заголовки могут содержать информацию о маршрутизации сообщений, безопасности, транзакциях, а также другие сведения в зависимости от служб, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="38f54-111">Headers may contain message routing, security information, transactions, and more depending on the services used by the application.</span></span> <span data-ttu-id="38f54-112">Как правило, по умолчанию выполняется шифрование сообщений.</span><span class="sxs-lookup"><span data-stu-id="38f54-112">Messages are typically encrypted by default.</span></span> <span data-ttu-id="38f54-113">Единственным исключением является использование привязки `BasicHttpBinding`, которая была создана для использования с небезопасными веб-службами прежних версий.</span><span class="sxs-lookup"><span data-stu-id="38f54-113">The one exception is when using the `BasicHttpBinding`, which was designed for use with non-secured, legacy Web services.</span></span> <span data-ttu-id="38f54-114">Разработчик приложения отвечает за окончательную версию приложения.</span><span class="sxs-lookup"><span data-stu-id="38f54-114">As the application designer, you are responsible for the final design.</span></span> <span data-ttu-id="38f54-115">Сообщения в тексте SOAP содержат данные конкретного приложения; Однако такие данные, как определенные приложением персональные данные, могут быть защищены с помощью функций шифрования и конфиденциальности WCF.</span><span class="sxs-lookup"><span data-stu-id="38f54-115">Messages in the SOAP body contain application-specific data; however, this data, such as application-defined personal information, can be secured by using WCF encryption or confidentiality features.</span></span> <span data-ttu-id="38f54-116">В следующих разделах описаны возможности, которые теоретически могут повлиять на конфиденциальность.</span><span class="sxs-lookup"><span data-stu-id="38f54-116">The following sections describe the features that potentially impact privacy.</span></span>  
  
## <a name="messaging"></a><span data-ttu-id="38f54-117">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="38f54-117">Messaging</span></span>  
 <span data-ttu-id="38f54-118">Каждое сообщение WCF имеет заголовок адреса, указывающий назначение сообщения и место, где должен быть отправлен ответ.</span><span class="sxs-lookup"><span data-stu-id="38f54-118">Each WCF message has an address header that specifies the message destination and where the reply should go.</span></span>  
  
 <span data-ttu-id="38f54-119">Компонент адреса конечной точки является универсальным кодом ресурса (URI), определяющим конечную точку.</span><span class="sxs-lookup"><span data-stu-id="38f54-119">The address component of an endpoint address is a Uniform Resource Identifier (URI) that identifies the endpoint.</span></span> <span data-ttu-id="38f54-120">Адрес может быть сетевым или логическим.</span><span class="sxs-lookup"><span data-stu-id="38f54-120">The address can be a network address or a logical address.</span></span> <span data-ttu-id="38f54-121">Адрес может содержать имя компьютера (имя узла, полное доменное имя) и IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="38f54-121">The address may include machine name (hostname, fully qualified domain name) and an IP address.</span></span> <span data-ttu-id="38f54-122">Адрес конечной точки также может содержать глобальный уникальный идентификатор (GUID) или коллекцию таких идентификаторов для временной адресации, используемой для распознавания каждого адреса.</span><span class="sxs-lookup"><span data-stu-id="38f54-122">The endpoint address may also contain a globally unique identifier (GUID), or a collection of GUIDs for temporary addressing used to discern each address.</span></span> <span data-ttu-id="38f54-123">Каждое сообщение содержит идентификатор сообщения, который является глобальным уникальным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="38f54-123">Each message contains a message ID that is a GUID.</span></span> <span data-ttu-id="38f54-124">Эта возможность соответствует стандарту ссылок WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="38f54-124">This feature follows the WS-Addressing reference standard.</span></span>  
  
 <span data-ttu-id="38f54-125">Уровень обмена сообщениями WCF не записывает персональные данные на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="38f54-125">The WCF messaging layer does not write any personal information to the local machine.</span></span> <span data-ttu-id="38f54-126">Однако возможно их распространение на уровне сети, если разработчик создал службу, раскрывающую такую информацию (например за счет указания имени пользователя в имени конечной точки или включения персональных данных в язык описания веб-служб конечной точки, но не требуя при этом от клиентов использования HTTPS для доступа к WSDL).</span><span class="sxs-lookup"><span data-stu-id="38f54-126">However, it might propagate personal information at the network level if a service developer has created a service that exposes such information (for example, by using a person's name in an endpoint name, or including personal information in the endpoint's Web Services Description Language but not requiring clients to use https to access the WSDL).</span></span> <span data-ttu-id="38f54-127">Кроме того, если разработчик запускает средство [служебной программы метаданных ServiceModel (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для конечной точки, предоставляющей персональные данные, выходные данные этого средства могут содержать эти сведения, а выходной файл записывается на локальный жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="38f54-127">Also, if a developer runs the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) tool against an endpoint that exposes personal information, the tool's output could contain that information, and the output file is written to the local hard disk.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="38f54-128">Размещение</span><span class="sxs-lookup"><span data-stu-id="38f54-128">Hosting</span></span>  
 <span data-ttu-id="38f54-129">Функция размещения в WCF позволяет запускать приложения по требованию или включать совместное использование портов несколькими приложениями.</span><span class="sxs-lookup"><span data-stu-id="38f54-129">The hosting feature in WCF allows applications to start on demand or to enable port sharing between multiple applications.</span></span> <span data-ttu-id="38f54-130">Приложение WCF может размещаться в службы IIS (IIS) аналогично ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="38f54-130">An WCF application can be hosted in Internet Information Services (IIS), similar to ASP.NET.</span></span>  
  
 <span data-ttu-id="38f54-131">При размещении не раскрывается какая-либо особая информация в сети, и данные не сохраняются на компьютере.</span><span class="sxs-lookup"><span data-stu-id="38f54-131">Hosting does not expose any specific information on the network and it does not keep data on the machine.</span></span>  
  
## <a name="message-security"></a><span data-ttu-id="38f54-132">Безопасность сообщений</span><span class="sxs-lookup"><span data-stu-id="38f54-132">Message Security</span></span>  
 <span data-ttu-id="38f54-133">Безопасность WCF предоставляет возможности безопасности для приложений обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="38f54-133">WCF security provides the security capabilities for messaging applications.</span></span> <span data-ttu-id="38f54-134">Предусмотренные функции безопасности включают в себя проверку подлинности и авторизацию.</span><span class="sxs-lookup"><span data-stu-id="38f54-134">The security functions provided include authentication and authorization.</span></span>  
  
 <span data-ttu-id="38f54-135">Проверка подлинности осуществляется путем передачи учетных данных между клиентами и службами.</span><span class="sxs-lookup"><span data-stu-id="38f54-135">Authentication is performed by passing credentials between the clients and services.</span></span> <span data-ttu-id="38f54-136">Проверка подлинности может выполняться либо через безопасность на транспортном уровне, либо через безопасность на уровне сообщений SOAP следующим образом.</span><span class="sxs-lookup"><span data-stu-id="38f54-136">Authentication can be either through transport-level security or through SOAP message-level security, as follows:</span></span>  
  
- <span data-ttu-id="38f54-137">При безопасности на уровне сообщений SOAP проверка подлинности осуществляется с помощью учетных данных, например имен пользователей/паролей, сертификатов X.509, билетов Kerberos и маркеров SAML, каждый из которых может содержать персональные данные в зависимости от издателя.</span><span class="sxs-lookup"><span data-stu-id="38f54-137">In SOAP message security, authentication is performed through credentials like username/passwords, X.509 certificates, Kerberos tickets, and SAML tokens, all of which might contain personal information, depending on the issuer.</span></span>  
  
- <span data-ttu-id="38f54-138">С помощью безопасности транспорта проверка подлинности осуществляется посредством таких обычных механизмов проверки подлинности транспорта, как схемы проверки подлинности HTTP (обычная, дайджест, Negotiate, Integrated Windows Authorization, NTLM, без проверки и анонимная) и проверка подлинности на основе формы.</span><span class="sxs-lookup"><span data-stu-id="38f54-138">Using transport security, authentication is done through traditional transport authentication mechanisms like HTTP authentication schemes (Basic, Digest, Negotiate, Integrated Windows Authorization, NTLM, None, and Anonymous), and form authentication.</span></span>  
  
 <span data-ttu-id="38f54-139">Результатом проверки подлинности может стать безопасный сеанс, осуществляемый между взаимодействующими конечными точками.</span><span class="sxs-lookup"><span data-stu-id="38f54-139">Authentication can result in a secure session established between the communicating endpoints.</span></span> <span data-ttu-id="38f54-140">Сеанс определяется идентификатором GUID, который существует на протяжении всего времени существования сеанса безопасности.</span><span class="sxs-lookup"><span data-stu-id="38f54-140">The session is identified by a GUID that lasts the lifetime of the security session.</span></span> <span data-ttu-id="38f54-141">В следующей таблице указано, что и где хранится.</span><span class="sxs-lookup"><span data-stu-id="38f54-141">The following table shows what is kept and where.</span></span>  
  
|<span data-ttu-id="38f54-142">Data</span><span class="sxs-lookup"><span data-stu-id="38f54-142">Data</span></span>|<span data-ttu-id="38f54-143">Система хранения данных</span><span class="sxs-lookup"><span data-stu-id="38f54-143">Storage</span></span>|  
|----------|-------------|  
|<span data-ttu-id="38f54-144">Учетные данные представления, например имена пользователей, сертификаты X.509, маркеры Kerberos и ссылки на учетные данные.</span><span class="sxs-lookup"><span data-stu-id="38f54-144">Presentation credentials, such as username, X.509 certificates, Kerberos tokens, and references to credentials.</span></span>|<span data-ttu-id="38f54-145">Стандартные механизмы управления учетными данными в Windows, например хранилище сертификатов Windows.</span><span class="sxs-lookup"><span data-stu-id="38f54-145">Standard Windows credential management mechanisms such as the Windows certificate store.</span></span>|  
|<span data-ttu-id="38f54-146">Информация о членстве пользователя, например имена пользователей и пароли.</span><span class="sxs-lookup"><span data-stu-id="38f54-146">User membership information, such as usernames and passwords.</span></span>|<span data-ttu-id="38f54-147">Поставщики членства ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="38f54-147">ASP.NET membership providers.</span></span>|  
|<span data-ttu-id="38f54-148">Данные идентификации о службе, используемой для проверки подлинности службы для клиентов.</span><span class="sxs-lookup"><span data-stu-id="38f54-148">Identity information about the service used to authenticate the service to clients.</span></span>|<span data-ttu-id="38f54-149">Адрес конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="38f54-149">Endpoint address of the service.</span></span>|  
|<span data-ttu-id="38f54-150">Сведения о вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="38f54-150">Caller information.</span></span>|<span data-ttu-id="38f54-151">Журналы аудита.</span><span class="sxs-lookup"><span data-stu-id="38f54-151">Auditing logs.</span></span>|  
  
## <a name="auditing"></a><span data-ttu-id="38f54-152">Аудит</span><span class="sxs-lookup"><span data-stu-id="38f54-152">Auditing</span></span>  
 <span data-ttu-id="38f54-153">Во время аудита регистрируются события успешной и неудачной проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="38f54-153">Auditing records the success and failure of authentication and authorization events.</span></span> <span data-ttu-id="38f54-154">В журналах аудита содержатся следующие данные: URI службы, URI действия и идентификация вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="38f54-154">Auditing records contain the following data: service URI, action URI, and the caller's identification.</span></span>  
  
 <span data-ttu-id="38f54-155">Во время аудита также регистрируется событие, когда администратор изменяет конфигурацию ведения журнала сообщений (включает или выключает), поскольку при ведении журнала сообщений данные, относящиеся к приложению, могут указываться в заголовках и телах.</span><span class="sxs-lookup"><span data-stu-id="38f54-155">Auditing also records when the administrator modifies the configuration of message logging (turning it on or off), because message logging may log application-specific data in headers and bodies.</span></span> <span data-ttu-id="38f54-156">В [!INCLUDE[wxp](../../../includes/wxp-md.md)] запись вносится в журнал событий приложений.</span><span class="sxs-lookup"><span data-stu-id="38f54-156">For [!INCLUDE[wxp](../../../includes/wxp-md.md)], a record is logged in the application event log.</span></span> <span data-ttu-id="38f54-157">Для Windows Vista и [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]запись записывается в журнал событий безопасности.</span><span class="sxs-lookup"><span data-stu-id="38f54-157">For Windows Vista and [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], a record is logged in the security event log.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="38f54-158">Транзакции</span><span class="sxs-lookup"><span data-stu-id="38f54-158">Transactions</span></span>  
 <span data-ttu-id="38f54-159">Функция Transactions предоставляет службы транзакций для приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="38f54-159">The transactions feature provides transactional services to a WCF application.</span></span>  
  
 <span data-ttu-id="38f54-160">Заголовки транзакций, используемые при распространении транзакций, могут содержать идентификаторы транзакций или идентификаторы зачисления, которые являются идентификаторами GUID.</span><span class="sxs-lookup"><span data-stu-id="38f54-160">Transaction headers used in transaction propagation may contain Transaction IDs or Enlistment IDs, which are GUIDs.</span></span>  
  
 <span data-ttu-id="38f54-161">Возможность транзакций использует диспетчер транзакций координатора распределенных транзакций (Майкрософт) (компонент Windows) для управления состоянием транзакций.</span><span class="sxs-lookup"><span data-stu-id="38f54-161">The Transactions feature uses the Microsoft Distributed Transaction Coordinator (MSDTC) Transaction Manager (a Windows component) to manage transaction state.</span></span> <span data-ttu-id="38f54-162">По умолчанию взаимодействие между диспетчерами транзакций шифруется.</span><span class="sxs-lookup"><span data-stu-id="38f54-162">By default, communications between Transactions Managers are encrypted.</span></span> <span data-ttu-id="38f54-163">Диспетчеры транзакций могут вносить в журнал ссылки на конечные точки, идентификаторы транзакций и идентификаторы зачисления как часть их устойчивого состояния.</span><span class="sxs-lookup"><span data-stu-id="38f54-163">Transaction Managers may log endpoint references, Transaction IDs, and Enlistment IDs as part of their durable state.</span></span> <span data-ttu-id="38f54-164">Время существования этого состояния определяется временем существования файла журнала диспетчера транзакций.</span><span class="sxs-lookup"><span data-stu-id="38f54-164">The lifetime of this state is determined by the lifetime of the Transaction Manager’s log file.</span></span> <span data-ttu-id="38f54-165">Этот журнал используется и обслуживается службой MSDTC.</span><span class="sxs-lookup"><span data-stu-id="38f54-165">The MSDTC service owns and maintains this log.</span></span>  
  
 <span data-ttu-id="38f54-166">Возможность транзакций реализует стандарты транзакций WS-Coordination и WS-Atomic.</span><span class="sxs-lookup"><span data-stu-id="38f54-166">The Transactions feature implements the WS-Coordination and WS-Atomic Transaction standards.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="38f54-167">Надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="38f54-167">Reliable Sessions</span></span>  
 <span data-ttu-id="38f54-168">Надежные сеансы в WCF обеспечивают передачу сообщений при возникновении транспортных или промежуточных сбоев.</span><span class="sxs-lookup"><span data-stu-id="38f54-168">Reliable sessions in WCF provide the transfer of messages when transport or intermediary failures occur.</span></span> <span data-ttu-id="38f54-169">Они обеспечивают точную передачу сообщений даже при отключении базового транспорта (например подключение TCP в беспроводной сети) или потере сообщения (удаление прокси-сервером HTTP исходящего или входящего сообщения).</span><span class="sxs-lookup"><span data-stu-id="38f54-169">They provide an exactly-once transfer of messages even when the underlying transport disconnects (for example, a TCP connection on a wireless network) or loses a message (an HTTP proxy dropping an outgoing or incoming message).</span></span> <span data-ttu-id="38f54-170">Надежные сеансы также восстанавливают измененный порядок передачи сообщений (что может произойти в случае многопутевой маршрутизации), сохраняя порядок, в котором были отправлены сообщения.</span><span class="sxs-lookup"><span data-stu-id="38f54-170">Reliable sessions also recover message reordering (as may happen in the case of multipath routing), preserving the order in which the messages were sent.</span></span>  
  
 <span data-ttu-id="38f54-171">Надежные сеансы реализованы с использованием протокола WS-ReliableMessaging (WS-RM).</span><span class="sxs-lookup"><span data-stu-id="38f54-171">Reliable sessions are implemented using the WS-ReliableMessaging (WS-RM) protocol.</span></span> <span data-ttu-id="38f54-172">Они добавляют заголовки WS-RM, содержащие информацию о сеансе, которая используется для определения всех сообщений, связанных с определенным надежным сеансом.</span><span class="sxs-lookup"><span data-stu-id="38f54-172">They add WS-RM headers that contain session information, which is used to identify all messages associated with a particular reliable session.</span></span> <span data-ttu-id="38f54-173">У каждого сеанса WS-RM имеется идентификатор, являющийся идентификатором GUID.</span><span class="sxs-lookup"><span data-stu-id="38f54-173">Each WS-RM session has an identifier, which is a GUID.</span></span>  
  
 <span data-ttu-id="38f54-174">Персональные данные на компьютере конечного пользователя не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="38f54-174">No personal information is retained on the end-user's machine.</span></span>  
  
## <a name="queued-channels"></a><span data-ttu-id="38f54-175">Очередь в каналах</span><span class="sxs-lookup"><span data-stu-id="38f54-175">Queued Channels</span></span>  
 <span data-ttu-id="38f54-176">В очередях хранятся сообщения отправляющего приложения от имени получающего приложения и позднее перенаправляющие эти сообщения получающему приложению.</span><span class="sxs-lookup"><span data-stu-id="38f54-176">Queues store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span> <span data-ttu-id="38f54-177">Они обеспечивают передачу сообщений из отправляющих в получающие приложения, когда, например, получающее приложение служит посредником.</span><span class="sxs-lookup"><span data-stu-id="38f54-177">They help ensure the transfer of messages from sending applications to receiving applications when, for example, the receiving application is transient.</span></span> <span data-ttu-id="38f54-178">WCF обеспечивает поддержку очереди с помощью службы очередей сообщений Майкрософт (MSMQ) в качестве транспорта.</span><span class="sxs-lookup"><span data-stu-id="38f54-178">WCF provides support for queuing by using Microsoft Message Queuing (MSMQ) as a transport.</span></span>  
  
 <span data-ttu-id="38f54-179">Функция очереди в каналах не добавляет заголовки в сообщение.</span><span class="sxs-lookup"><span data-stu-id="38f54-179">The queued channels feature does not add headers to a message.</span></span> <span data-ttu-id="38f54-180">Вместо этого она создает сообщение очереди сообщений с соответствующим набором свойств этого сообщения и вызывает методы очереди сообщений, чтобы разместить сообщение в очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="38f54-180">Instead it creates a Message Queuing message with appropriate Message Queuing message properties set, and invokes Message Queuing methods to put the message in the Message Queuing queue.</span></span> <span data-ttu-id="38f54-181">Очередь сообщений является необязательным компонентом в поставляемой ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="38f54-181">Message Queuing is an optional component that ships with Windows.</span></span>  
  
 <span data-ttu-id="38f54-182">Возможность очереди в каналах не сохраняет информацию на компьютере конечного пользователя, поскольку она использует очередь сообщений в качестве инфраструктуры организации очередей.</span><span class="sxs-lookup"><span data-stu-id="38f54-182">No information is retained on the end-user's machine by the queued channels feature, because it uses Message Queuing as the queuing infrastructure.</span></span>  
  
## <a name="com-integration"></a><span data-ttu-id="38f54-183">Интеграция с COM+</span><span class="sxs-lookup"><span data-stu-id="38f54-183">COM+ Integration</span></span>  
 <span data-ttu-id="38f54-184">Эта функция заключает существующие функциональные возможности COM и COM+ для создания служб, совместимых со службами WCF.</span><span class="sxs-lookup"><span data-stu-id="38f54-184">This feature wraps existing COM and COM+ functionality to create services that are compatible with WCF services.</span></span> <span data-ttu-id="38f54-185">В этой возможности не используются специальные заголовки, и она не хранит данные на компьютере конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="38f54-185">This feature does not use specific headers and it does not retain data on the end-user's machine.</span></span>  
  
## <a name="com-service-moniker"></a><span data-ttu-id="38f54-186">Моникер служб COM</span><span class="sxs-lookup"><span data-stu-id="38f54-186">COM Service Moniker</span></span>  
 <span data-ttu-id="38f54-187">Это обеспечивает неуправляемую оболочку для стандартного клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="38f54-187">This provides an unmanaged wrapper to a standard WCF client.</span></span> <span data-ttu-id="38f54-188">В этой возможности по сети не передаются специальные заголовки, и она не хранит данные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="38f54-188">This feature does not have specific headers on the wire nor does it persist data on the machine.</span></span>  
  
## <a name="peer-channel"></a><span data-ttu-id="38f54-189">Одноранговый канал</span><span class="sxs-lookup"><span data-stu-id="38f54-189">Peer Channel</span></span>  
 <span data-ttu-id="38f54-190">Одноранговый канал позволяет разрабатывать многокомпонентные приложения с помощью WCF.</span><span class="sxs-lookup"><span data-stu-id="38f54-190">A peer channel enables development of multiparty applications using WCF.</span></span> <span data-ttu-id="38f54-191">Многопользовательский обмен сообщениями возникает в контексте сетки.</span><span class="sxs-lookup"><span data-stu-id="38f54-191">Multiparty messaging occurs in the context of a mesh.</span></span> <span data-ttu-id="38f54-192">Сетки определяются именем, с которым узел может соединиться.</span><span class="sxs-lookup"><span data-stu-id="38f54-192">Meshes are identified by a name that nodes can join.</span></span> <span data-ttu-id="38f54-193">Каждый узел в одноранговом канале создает прослушиватель TCP на указанном пользователем порту и устанавливает подключения к другим узлам в сетке, чтобы обеспечить устойчивую работу.</span><span class="sxs-lookup"><span data-stu-id="38f54-193">Each node in the peer channel creates a TCP listener at a user-specified port and establishes connections with other nodes in the mesh to ensure resiliency.</span></span> <span data-ttu-id="38f54-194">Чтобы подключиться к другим узлам в сетке, узлы также обмениваются некоторыми данными, включая адрес прослушивателя и IP-адреса компьютера, с другими узлами в сетке.</span><span class="sxs-lookup"><span data-stu-id="38f54-194">To connect to other nodes in the mesh, nodes also exchange some data, including the listener address and the machine's IP addresses, with other nodes in the mesh.</span></span> <span data-ttu-id="38f54-195">Сообщения, отправляемые по сетке, могут содержать сведения о безопасности, принадлежащие отправителю, с целью предотвращения спуфинга и подделки сообщений.</span><span class="sxs-lookup"><span data-stu-id="38f54-195">Messages sent around in the mesh can contain security information that pertains to the sender to prevent message spoofing and tampering.</span></span>  
  
 <span data-ttu-id="38f54-196">Персональные данные на компьютере конечного пользователя не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="38f54-196">No personal information is stored on the end-user's machine.</span></span>  
  
## <a name="it-professional-experience"></a><span data-ttu-id="38f54-197">Опыт работы ИТ-специалистов</span><span class="sxs-lookup"><span data-stu-id="38f54-197">IT Professional Experience</span></span>  
  
### <a name="tracing"></a><span data-ttu-id="38f54-198">Трассировка</span><span class="sxs-lookup"><span data-stu-id="38f54-198">Tracing</span></span>  
 <span data-ttu-id="38f54-199">Функция диагностики инфраструктуры WCF регистрирует сообщения, которые проходят через уровни модели транспорта и службы, а также действия и события, связанные с этими сообщениями.</span><span class="sxs-lookup"><span data-stu-id="38f54-199">The diagnostics feature of the WCF infrastructure logs messages that pass through the transport and service model layers, and the activities and events associated with these messages.</span></span> <span data-ttu-id="38f54-200">Эта возможность отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38f54-200">This feature is turned off by default.</span></span> <span data-ttu-id="38f54-201">Он включается с помощью файла конфигурации приложения, и поведение трассировки может быть изменено с помощью поставщика WCF WMI во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="38f54-201">It is enabled using the application’s configuration file and the tracing behavior may be modified using the WCF WMI provider at run time.</span></span> <span data-ttu-id="38f54-202">Во включенном состоянии инфраструктура трассировки выдает настроенным прослушивателям диагностическую трассировку, содержащую сообщения, действия и события обработки.</span><span class="sxs-lookup"><span data-stu-id="38f54-202">When enabled, the tracing infrastructure emits a diagnostic trace that contains messages, activities, and processing events to configured listeners.</span></span> <span data-ttu-id="38f54-203">Формат и расположение выходных данных определяются выбранной администратором конфигурацией прослушивателя, однако, как правило, это файл в формате XML.</span><span class="sxs-lookup"><span data-stu-id="38f54-203">The format and location of the output are determined by the administrator’s listener configuration choices, but is typically an XML formatted file.</span></span> <span data-ttu-id="38f54-204">Администратор отвечает за настройку списка управления доступом (ACL) для файлов трассировки.</span><span class="sxs-lookup"><span data-stu-id="38f54-204">The administrator is responsible for setting the access control list (ACL) on the trace files.</span></span> <span data-ttu-id="38f54-205">В частности, в случае размещения в системе Windows Activation System (WAS) администратор должен убедиться, что файлы не предоставляются с общедоступного виртуального корневого каталога, за исключением, если это сделано намеренно.</span><span class="sxs-lookup"><span data-stu-id="38f54-205">In particular, when hosted by Windows Activation System (WAS), the administrator should make sure the files are not served from the public virtual root directory if that is not desired.</span></span>  
  
 <span data-ttu-id="38f54-206">Существует два типа трассировки: ведение журналов сообщений и диагностическая трассировка модели служб, описание см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="38f54-206">There are two types of tracing: Message logging and Service Model diagnostic tracing, described in the following section.</span></span> <span data-ttu-id="38f54-207">Каждый тип настраивается через собственный источник трассировки: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> и <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="38f54-207">Each type is configured through its own trace source: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> and <xref:System.ServiceModel>.</span></span> <span data-ttu-id="38f54-208">Оба этих источника трассировки для ведения журналов собирают данные, являющиеся локальными для приложения.</span><span class="sxs-lookup"><span data-stu-id="38f54-208">Both of these logging trace sources capture data that is local to the application.</span></span>  
  
### <a name="message-logging"></a><span data-ttu-id="38f54-209">Ведение журналов сообщений</span><span class="sxs-lookup"><span data-stu-id="38f54-209">Message Logging</span></span>  
 <span data-ttu-id="38f54-210">Источник трассировки для ведения журнала сообщений (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) позволяет администратору вносить в журнал передаваемые в системе сообщения.</span><span class="sxs-lookup"><span data-stu-id="38f54-210">The message logging trace source (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) allows an administrator to log the messages that flow through the system.</span></span> <span data-ttu-id="38f54-211">С помощью конфигурации пользователь может выбрать, следует ли вносить в журнал сообщения целиком или только их заголовки, либо вносить их в журнал на транспортном уровне или уровне модели службы, либо включать неправильно сформированные сообщения.</span><span class="sxs-lookup"><span data-stu-id="38f54-211">Through configuration, the user may decide to log entire messages or message headers only, whether to log at the transport and/or service model layers, and whether to include malformed messages.</span></span> <span data-ttu-id="38f54-212">Кроме того, пользователь может настроить фильтрацию, чтобы ограничить внесение сообщений в журнал определенными типами.</span><span class="sxs-lookup"><span data-stu-id="38f54-212">Also, the user may configure filtering to restrict which messages are logged.</span></span>  
  
 <span data-ttu-id="38f54-213">По умолчанию ведение журнала сообщений отключено.</span><span class="sxs-lookup"><span data-stu-id="38f54-213">By default, message logging is disabled.</span></span> <span data-ttu-id="38f54-214">Администратор локального компьютера может запретить администратору на уровне приложения включение ведения журнала сообщений.</span><span class="sxs-lookup"><span data-stu-id="38f54-214">The local machine administrator can prevent the application-level administrator from turning message logging on.</span></span>  
  
#### <a name="encrypted-and-decrypted-message-logging"></a><span data-ttu-id="38f54-215">Ведение журнала зашифрованных и расшифрованных сообщений</span><span class="sxs-lookup"><span data-stu-id="38f54-215">Encrypted and Decrypted Message Logging</span></span>  
 <span data-ttu-id="38f54-216">Зашифрованные или расшифрованные сообщения вносятся в журнал в соответствии со следующими условиями.</span><span class="sxs-lookup"><span data-stu-id="38f54-216">Messages are logged, encrypted, or decrypted, as described in the following terms.</span></span>  
  
 <span data-ttu-id="38f54-217">Ведение журнала транспорта</span><span class="sxs-lookup"><span data-stu-id="38f54-217">Transport Logging</span></span>  
 <span data-ttu-id="38f54-218">Внесение в журнал сообщений, получаемых и отправляемых на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="38f54-218">Logs messages received and sent at the transport level.</span></span> <span data-ttu-id="38f54-219">Эти сообщения содержат все заголовки и могут быть зашифрованы перед отправкой по сети и во время получения.</span><span class="sxs-lookup"><span data-stu-id="38f54-219">These messages contain all headers, and may be encrypted before being sent on the wire and when being received.</span></span>  
  
 <span data-ttu-id="38f54-220">Если сообщения зашифрованы перед отправкой по сети и во время получения, они вносятся в журнал как зашифрованные.</span><span class="sxs-lookup"><span data-stu-id="38f54-220">If messages are encrypted before being sent on the wire and when they are received, they are logged encrypted as well.</span></span> <span data-ttu-id="38f54-221">Исключением является использование протокола безопасности (HTTPS): в этом случае они вносятся в журнал расшифрованными перед отправкой и после получения, даже если они зашифровываются в сети.</span><span class="sxs-lookup"><span data-stu-id="38f54-221">An exception is when a security protocol is used (https): they are then logged decrypted before being sent and after being received even if they are encrypted on the wire.</span></span>  
  
 <span data-ttu-id="38f54-222">Ведение журнала служб</span><span class="sxs-lookup"><span data-stu-id="38f54-222">Service Logging</span></span>  
 <span data-ttu-id="38f54-223">Внесение в журнал сообщений, полученных или отправленных на уровне модели служб, после обработки заголовка канала, непосредственно перед и после ввода пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="38f54-223">Logs messages received or sent at the service model level, after channel header processing has occurred, just before and after entering user code.</span></span>  
  
 <span data-ttu-id="38f54-224">Сообщения, внесенные в журнал на этом уровне, расшифровываются, даже если они были защищены и зашифрованы в сети.</span><span class="sxs-lookup"><span data-stu-id="38f54-224">Messages logged at this level are decrypted even if they were secured and encrypted on the wire.</span></span>  
  
 <span data-ttu-id="38f54-225">Ведение журнала неправильно сформированных сообщений</span><span class="sxs-lookup"><span data-stu-id="38f54-225">Malformed Message Logging</span></span>  
 <span data-ttu-id="38f54-226">Записывает в журнал сообщения, которые инфраструктура WCF не может распознать или обработать.</span><span class="sxs-lookup"><span data-stu-id="38f54-226">Logs messages that the WCF infrastructure cannot understand or process.</span></span>  
  
 <span data-ttu-id="38f54-227">Сообщения вносятся в журнал «как есть», т.е. либо зашифрованными, либо расшифрованными.</span><span class="sxs-lookup"><span data-stu-id="38f54-227">Messages are logged as-is, that is, encrypted or not</span></span>  
  
 <span data-ttu-id="38f54-228">Когда сообщения регистрируются в расшифрованной или незашифрованной форме, по умолчанию WCF удаляет ключи безопасности и потенциально персональные данные из сообщений перед их регистрацией.</span><span class="sxs-lookup"><span data-stu-id="38f54-228">When messages are logged in decrypted or unencrypted form, by default WCF removes security keys and potentially personal information from the messages before logging them.</span></span> <span data-ttu-id="38f54-229">В следующих разделах представлено описание, какая информация удаляется и когда.</span><span class="sxs-lookup"><span data-stu-id="38f54-229">The next sections describe what information is removed, and when.</span></span> <span data-ttu-id="38f54-230">Администратор компьютера и специалист, выполняющий развертывание приложения, должны предпринять ряд действий в отношении конфигурации, чтобы изменить поведение по умолчанию, связанное с внесением в журнал ключей и потенциально персональных данных.</span><span class="sxs-lookup"><span data-stu-id="38f54-230">The machine administrator and application deployer must both take certain configuration actions to change the default behavior to log keys and potentially personal information.</span></span>  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="38f54-231">Информация, удаленная из заголовков сообщений при внесении в журнал зашифрованных/незашифрованных сообщений</span><span class="sxs-lookup"><span data-stu-id="38f54-231">Information Removed from Message Headers When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="38f54-232">Когда сообщения вносятся в журнал в зашифрованной или незашифрованной форме, ключи безопасности и потенциально персональные данные по умолчанию удаляются из заголовков и тел сообщений перед тем, как они будут внесены в журнал.</span><span class="sxs-lookup"><span data-stu-id="38f54-232">When messages are logged in decrypted/unencrypted form, security keys and potentially personal information are removed by default from message headers and message bodies before they are logged.</span></span> <span data-ttu-id="38f54-233">В следующем списке показано, что WCF учитывает ключи и потенциально персональные данные.</span><span class="sxs-lookup"><span data-stu-id="38f54-233">The following list shows what WCF considers keys and potentially personal information.</span></span>  
  
 <span data-ttu-id="38f54-234">Удаляемые ключи:</span><span class="sxs-lookup"><span data-stu-id="38f54-234">Keys that are removed:</span></span>  
  
 <span data-ttu-id="38f54-235">\- Xmlns:wst ="http://schemas.xmlsoap.org/ws/2004/04/trust" и xmlns:wst ="http://schemas.xmlsoap.org/ws/2005/02/trust"</span><span class="sxs-lookup"><span data-stu-id="38f54-235">\- For xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"</span></span>  
  
 <span data-ttu-id="38f54-236">wst:BinarySecret</span><span class="sxs-lookup"><span data-stu-id="38f54-236">wst:BinarySecret</span></span>  
  
 <span data-ttu-id="38f54-237">wst:Entropy</span><span class="sxs-lookup"><span data-stu-id="38f54-237">wst:Entropy</span></span>  
  
 <span data-ttu-id="38f54-238">\- Xmlns:wsse ="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" и xmlns:wsse ="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="38f54-238">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="38f54-239">wsse:Password</span><span class="sxs-lookup"><span data-stu-id="38f54-239">wsse:Password</span></span>  
  
 <span data-ttu-id="38f54-240">wsse:Nonce</span><span class="sxs-lookup"><span data-stu-id="38f54-240">wsse:Nonce</span></span>  
  
 <span data-ttu-id="38f54-241">Удаляемые потенциально персональные данные:</span><span class="sxs-lookup"><span data-stu-id="38f54-241">Potentially personal information that is removed:</span></span>  
  
 <span data-ttu-id="38f54-242">\- Xmlns:wsse ="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" и xmlns:wsse ="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="38f54-242">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="38f54-243">wsse:Username</span><span class="sxs-lookup"><span data-stu-id="38f54-243">wsse:Username</span></span>  
  
 <span data-ttu-id="38f54-244">wsse:BinarySecurityToken</span><span class="sxs-lookup"><span data-stu-id="38f54-244">wsse:BinarySecurityToken</span></span>  
  
 <span data-ttu-id="38f54-245">\- для xmlns: SAML = "urn: Oasis: Names: TC: SAML: 1.0: assertion" элементы, выделенные жирным шрифтом (ниже), удаляются:</span><span class="sxs-lookup"><span data-stu-id="38f54-245">\- For xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" the items in bold (below) are removed:</span></span>  
  
 <span data-ttu-id="38f54-246">Утверждение \<</span><span class="sxs-lookup"><span data-stu-id="38f54-246">\<Assertion</span></span>  
  
 <span data-ttu-id="38f54-247">MajorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="38f54-247">MajorVersion="1"</span></span>  
  
 <span data-ttu-id="38f54-248">MinorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="38f54-248">MinorVersion="1"</span></span>  
  
 <span data-ttu-id="38f54-249">AssertionId="[ID]"</span><span class="sxs-lookup"><span data-stu-id="38f54-249">AssertionId="[ID]"</span></span>  
  
 <span data-ttu-id="38f54-250">Issuer="[string]"</span><span class="sxs-lookup"><span data-stu-id="38f54-250">Issuer="[string]"</span></span>  
  
 <span data-ttu-id="38f54-251">IssueInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="38f54-251">IssueInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="38f54-252">\<Conditions NotBefore = "[dateTime]" Нотонорафтер = "[dateTime]" ></span><span class="sxs-lookup"><span data-stu-id="38f54-252">\<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]"></span></span>  
  
 <span data-ttu-id="38f54-253">\<AudienceRestrictionCondition ></span><span class="sxs-lookup"><span data-stu-id="38f54-253">\<AudienceRestrictionCondition></span></span>  
  
 <span data-ttu-id="38f54-254">\<аудитория > [URI]\</Аудиенце > +</span><span class="sxs-lookup"><span data-stu-id="38f54-254">\<Audience>[uri]\</Audience>+</span></span>  
  
 <span data-ttu-id="38f54-255">\</Аудиенцерестриктионкондитион > \*</span><span class="sxs-lookup"><span data-stu-id="38f54-255">\</AudienceRestrictionCondition>\*</span></span>  
  
 <span data-ttu-id="38f54-256">\<DoNotCacheCondition/> \*</span><span class="sxs-lookup"><span data-stu-id="38f54-256">\<DoNotCacheCondition />\*</span></span>  
  
 <span data-ttu-id="38f54-257"><\!--абстрактный базовый тип</span><span class="sxs-lookup"><span data-stu-id="38f54-257"><\!-- abstract base type</span></span>  
  
 <span data-ttu-id="38f54-258">\<условие или > \*</span><span class="sxs-lookup"><span data-stu-id="38f54-258">\<Condition />\*</span></span>  
  
 -->  
  
 <span data-ttu-id="38f54-259">\</Кондитионс >?</span><span class="sxs-lookup"><span data-stu-id="38f54-259">\</Conditions>?</span></span>  
  
 <span data-ttu-id="38f54-260">\<советы ></span><span class="sxs-lookup"><span data-stu-id="38f54-260">\<Advice></span></span>  
  
 <span data-ttu-id="38f54-261">\<Ассертионидреференце > [ID]\</Ассертионидреференце > \*</span><span class="sxs-lookup"><span data-stu-id="38f54-261">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span></span>  
  
 <span data-ttu-id="38f54-262">Утверждение \<> [утверждение]\</Ассертион > \*</span><span class="sxs-lookup"><span data-stu-id="38f54-262">\<Assertion>[assertion]\</Assertion>\*</span></span>  
  
 <span data-ttu-id="38f54-263">[any]\*</span><span class="sxs-lookup"><span data-stu-id="38f54-263">[any]\*</span></span>  
  
 <span data-ttu-id="38f54-264">\</Адвице >?</span><span class="sxs-lookup"><span data-stu-id="38f54-264">\</Advice>?</span></span>  
  
 <span data-ttu-id="38f54-265"><\!--абстрактные базовые типы</span><span class="sxs-lookup"><span data-stu-id="38f54-265"><\!-- Abstract base types</span></span>  
  
 <span data-ttu-id="38f54-266">\<ная инструкция/> \*</span><span class="sxs-lookup"><span data-stu-id="38f54-266">\<Statement />\*</span></span>  
  
 <span data-ttu-id="38f54-267">\<Субжектстатемент ></span><span class="sxs-lookup"><span data-stu-id="38f54-267">\<SubjectStatement></span></span>  
  
 <span data-ttu-id="38f54-268">\<> субъекта</span><span class="sxs-lookup"><span data-stu-id="38f54-268">\<Subject></span></span>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 <span data-ttu-id="38f54-269">\<SubjectConfirmation ></span><span class="sxs-lookup"><span data-stu-id="38f54-269">\<SubjectConfirmation></span></span>  
  
 <span data-ttu-id="38f54-270">\<ConfirmationMethod > [anyUri]\</Конфирматионмесод > +</span><span class="sxs-lookup"><span data-stu-id="38f54-270">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span></span>  
  
 <span data-ttu-id="38f54-271">\<SubjectConfirmationData > [Any]\</Субжектконфирматиондата >?</span><span class="sxs-lookup"><span data-stu-id="38f54-271">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span></span>  
  
 <span data-ttu-id="38f54-272">\<DS: KeyInfo >...\</ДС: KeyInfo >?</span><span class="sxs-lookup"><span data-stu-id="38f54-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span></span>  
  
 <span data-ttu-id="38f54-273">\</Субжектконфирматион >?</span><span class="sxs-lookup"><span data-stu-id="38f54-273">\</SubjectConfirmation>?</span></span>  
  
 <span data-ttu-id="38f54-274">\</Субжект ></span><span class="sxs-lookup"><span data-stu-id="38f54-274">\</Subject></span></span>  
  
 <span data-ttu-id="38f54-275">\</Субжектстатемент > \*</span><span class="sxs-lookup"><span data-stu-id="38f54-275">\</SubjectStatement>\*</span></span>  
  
 -->  
  
 <span data-ttu-id="38f54-276">\<AuthenticationStatement</span><span class="sxs-lookup"><span data-stu-id="38f54-276">\<AuthenticationStatement</span></span>  
  
 <span data-ttu-id="38f54-277">AuthenticationMethod="[uri]"</span><span class="sxs-lookup"><span data-stu-id="38f54-277">AuthenticationMethod="[uri]"</span></span>  
  
 <span data-ttu-id="38f54-278">AuthenticationInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="38f54-278">AuthenticationInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="38f54-279">[Subject]</span><span class="sxs-lookup"><span data-stu-id="38f54-279">[Subject]</span></span>  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <span data-ttu-id="38f54-280">< AuthorityBinding</span><span class="sxs-lookup"><span data-stu-id="38f54-280"><AuthorityBinding</span></span>  
  
 <span data-ttu-id="38f54-281">AuthorityKind="[QName]"</span><span class="sxs-lookup"><span data-stu-id="38f54-281">AuthorityKind="[QName]"</span></span>  
  
 <span data-ttu-id="38f54-282">Location="[uri]"</span><span class="sxs-lookup"><span data-stu-id="38f54-282">Location="[uri]"</span></span>  
  
 <span data-ttu-id="38f54-283">Binding="[uri]"</span><span class="sxs-lookup"><span data-stu-id="38f54-283">Binding="[uri]"</span></span>  
  
 />*  
  
 <span data-ttu-id="38f54-284">\</Аусентикатионстатемент > \*</span><span class="sxs-lookup"><span data-stu-id="38f54-284">\</AuthenticationStatement>\*</span></span>  
  
 <span data-ttu-id="38f54-285">\<AttributeStatement ></span><span class="sxs-lookup"><span data-stu-id="38f54-285">\<AttributeStatement></span></span>  
  
 <span data-ttu-id="38f54-286">[Subject]</span><span class="sxs-lookup"><span data-stu-id="38f54-286">[Subject]</span></span>  
  
 <span data-ttu-id="38f54-287">Атрибут \<</span><span class="sxs-lookup"><span data-stu-id="38f54-287">\<Attribute</span></span>  
  
 <span data-ttu-id="38f54-288">AttributeName="[string]"</span><span class="sxs-lookup"><span data-stu-id="38f54-288">AttributeName="[string]"</span></span>  
  
 <span data-ttu-id="38f54-289">AttributeNamespace="[uri]"</span><span class="sxs-lookup"><span data-stu-id="38f54-289">AttributeNamespace="[uri]"</span></span>  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 <span data-ttu-id="38f54-290">\</аттрибуте > +</span><span class="sxs-lookup"><span data-stu-id="38f54-290">\</Attribute>+</span></span>  
  
 <span data-ttu-id="38f54-291">\</Аттрибутестатемент > \*</span><span class="sxs-lookup"><span data-stu-id="38f54-291">\</AttributeStatement>\*</span></span>  
  
 <span data-ttu-id="38f54-292">\<AuthorizationDecisionStatement</span><span class="sxs-lookup"><span data-stu-id="38f54-292">\<AuthorizationDecisionStatement</span></span>  
  
 <span data-ttu-id="38f54-293">Resource="[uri]"</span><span class="sxs-lookup"><span data-stu-id="38f54-293">Resource="[uri]"</span></span>  
  
 <span data-ttu-id="38f54-294">Решение = "[Разрешить&#124;запрет&#124;не определено]"</span><span class="sxs-lookup"><span data-stu-id="38f54-294">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span></span>  
  
 >  
  
 <span data-ttu-id="38f54-295">[Subject]</span><span class="sxs-lookup"><span data-stu-id="38f54-295">[Subject]</span></span>  
  
 <span data-ttu-id="38f54-296">\<Action Namespace = "[URI]" > [строка]\</Action > +</span><span class="sxs-lookup"><span data-stu-id="38f54-296">\<Action Namespace="[uri]">[string]\</Action>+</span></span>  
  
 <span data-ttu-id="38f54-297">\<> свидетельства</span><span class="sxs-lookup"><span data-stu-id="38f54-297">\<Evidence></span></span>  
  
 <span data-ttu-id="38f54-298">\<Ассертионидреференце > [ID]\</Ассертионидреференце > +</span><span class="sxs-lookup"><span data-stu-id="38f54-298">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span></span>  
  
 <span data-ttu-id="38f54-299">Утверждение \<> [assertion]\</Ассертион > +</span><span class="sxs-lookup"><span data-stu-id="38f54-299">\<Assertion>[assertion]\</Assertion>+</span></span>  
  
 <span data-ttu-id="38f54-300">\</Евиденце >?</span><span class="sxs-lookup"><span data-stu-id="38f54-300">\</Evidence>?</span></span>  
  
 <span data-ttu-id="38f54-301">\</АусоризатиондеЦисионстатемент > \*</span><span class="sxs-lookup"><span data-stu-id="38f54-301">\</AuthorizationDecisionStatement>\*</span></span>  
  
 <span data-ttu-id="38f54-302">\</Ассертион ></span><span class="sxs-lookup"><span data-stu-id="38f54-302">\</Assertion></span></span>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="38f54-303">Информация, удаленная из тел сообщений при внесении в журнал зашифрованных/незашифрованных сообщений</span><span class="sxs-lookup"><span data-stu-id="38f54-303">Information Removed from Message Bodies When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="38f54-304">Как было сказано выше, WCF удаляет ключи и известные потенциально персональные данные из заголовков сообщений для зарегистрированных расшифрованных и незашифрованных сообщений.</span><span class="sxs-lookup"><span data-stu-id="38f54-304">As previously described, WCF removes keys and known potentially personal information from message headers for logged decrypted/unencrypted messages.</span></span> <span data-ttu-id="38f54-305">Кроме того, WCF удаляет ключи и известные потенциально персональные данные из тела сообщений для элементов текста и действий в следующем списке, описывающих сообщения безопасности, связанные с обменом ключами.</span><span class="sxs-lookup"><span data-stu-id="38f54-305">In addition, WCF removes keys and known potentially personal information from message bodies for the body elements and actions in the following list, which describe security messages involved in key exchange.</span></span>  
  
 <span data-ttu-id="38f54-306">Для следующих пространств имен:</span><span class="sxs-lookup"><span data-stu-id="38f54-306">For the following namespaces:</span></span>  
  
 <span data-ttu-id="38f54-307">xmlns:WST ="http://schemas.xmlsoap.org/ws/2004/04/trust" и xmlns:wst =» http://schemas.xmlsoap.org/ws/2005/02/trust" (например, если нет действия)</span><span class="sxs-lookup"><span data-stu-id="38f54-307">xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" (for example, if no action available)</span></span>  
  
 <span data-ttu-id="38f54-308">Информация удаляется для элементов тел, участвующих в обмене ключами:</span><span class="sxs-lookup"><span data-stu-id="38f54-308">Information is removed for these body elements, which involve key exchange:</span></span>  
  
 <span data-ttu-id="38f54-309">wst:RequestSecurityToken</span><span class="sxs-lookup"><span data-stu-id="38f54-309">wst:RequestSecurityToken</span></span>  
  
 <span data-ttu-id="38f54-310">wst:RequestSecurityTokenResponse</span><span class="sxs-lookup"><span data-stu-id="38f54-310">wst:RequestSecurityTokenResponse</span></span>  
  
 <span data-ttu-id="38f54-311">wst:RequestSecurityTokenResponseCollection</span><span class="sxs-lookup"><span data-stu-id="38f54-311">wst:RequestSecurityTokenResponseCollection</span></span>  
  
 <span data-ttu-id="38f54-312">Информация также удаляется для каждого из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="38f54-312">Information is also removed for each of the following Actions:</span></span>  
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend`
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a><span data-ttu-id="38f54-313">Информация не удаляется из данных заголовков и тел, относящихся к приложению</span><span class="sxs-lookup"><span data-stu-id="38f54-313">No Information Is Removed from Application-specific Headers and Body Data</span></span>  
 <span data-ttu-id="38f54-314">WCF не следит за личными данными в заголовках приложений (например, строках запросов) или данных текста (например, номер кредитной карты).</span><span class="sxs-lookup"><span data-stu-id="38f54-314">WCF does not track personal information in application-specific headers (for example, query strings) or body data (for example, credit card number).</span></span>  
  
 <span data-ttu-id="38f54-315">Когда включено ведение журнала сообщений, персональные данные в информации заголовков и тел, относящихся к приложению, могут отображаться в журналах.</span><span class="sxs-lookup"><span data-stu-id="38f54-315">When message logging is on, personal information in application-specific headers and body information may be visible in the logs.</span></span> <span data-ttu-id="38f54-316">И вновь, специалист, выполняющий развертывание приложения, отвечает за настройку элементов управления доступом для файлов конфигурации и журналов.</span><span class="sxs-lookup"><span data-stu-id="38f54-316">Again, the application deployer is responsible for setting the ACLs on the configuration and log files.</span></span> <span data-ttu-id="38f54-317">Он также может отключить ведение журнала, если отображение такой информации не требуется, или отфильтровать эту информацию из файлов журнала после ее внесения в журнал.</span><span class="sxs-lookup"><span data-stu-id="38f54-317">He also can turn off logging if he does not want this information to be visible, or he may filter out this information from the log files after it is logged.</span></span>  
  
### <a name="service-model-tracing"></a><span data-ttu-id="38f54-318">Трассировка модели службы</span><span class="sxs-lookup"><span data-stu-id="38f54-318">Service Model Tracing</span></span>  
 <span data-ttu-id="38f54-319">Источник трассировки модели службы (<xref:System.ServiceModel>) обеспечивает трассировку действий и событий, относящихся к обработке сообщений.</span><span class="sxs-lookup"><span data-stu-id="38f54-319">The Service Model trace source (<xref:System.ServiceModel>) enables tracing of activities and events related to message processing.</span></span> <span data-ttu-id="38f54-320">Эта возможность использует диагностические возможности .NET Framework из <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="38f54-320">This feature uses the .NET Framework diagnostic functionality from <xref:System.Diagnostics>.</span></span> <span data-ttu-id="38f54-321">Аналогично свойству <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>, ее расположение и элемент управления доступом настраиваются пользователем с помощью файлов конфигурации приложения на базе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38f54-321">As with the <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> property, the location and its ACL are user-configurable using .NET Framework application configuration files.</span></span> <span data-ttu-id="38f54-322">Как и при ведении журнала сообщений, расположение файла всегда настраивается при включении администратором трассировки. Таким образом, администратор управляет элементом управления доступом.</span><span class="sxs-lookup"><span data-stu-id="38f54-322">As with message logging, the file location is always configured when the administrator enables tracing; thus, the administrator controls the ACL.</span></span>  
  
 <span data-ttu-id="38f54-323">Трассировки содержат заголовки сообщений, когда сообщения находятся в области действия.</span><span class="sxs-lookup"><span data-stu-id="38f54-323">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="38f54-324">Применяются аналогичные правила скрытия потенциально персональных данных в заголовках сообщений, описанные в предыдущем разделе: ранее определенные персональные данные по умолчанию удаляются из заголовков в трассировках.</span><span class="sxs-lookup"><span data-stu-id="38f54-324">The same rules for hiding potentially personal information in message headers in the previous section apply: the personal information previously identified is removed by default from the headers in traces.</span></span> <span data-ttu-id="38f54-325">Администратор компьютера и специалист, выполняющий развертывание приложения, должны изменить конфигурацию, чтобы вносить в журнал потенциально персональные сведения.</span><span class="sxs-lookup"><span data-stu-id="38f54-325">Both the machine administrator and the application deployer must modify the configuration in order to log potentially personal information.</span></span> <span data-ttu-id="38f54-326">Однако персональные данные в заголовках, относящихся к приложению, вносятся в журнал в трассировках.</span><span class="sxs-lookup"><span data-stu-id="38f54-326">However, personal information contained in application-specific headers is logged in traces.</span></span> <span data-ttu-id="38f54-327">Специалист, выполняющий развертывание приложения, отвечает за настройку элементов управления доступом в файлах конфигурации и трассировки.</span><span class="sxs-lookup"><span data-stu-id="38f54-327">The application deployer is responsible for setting the ACLs on the configuration and trace files.</span></span> <span data-ttu-id="38f54-328">Он также может отключить трассировку, если отображение такой информации не требуется, или отфильтровать эту информацию из файлов трассировки после ее внесения в журнал.</span><span class="sxs-lookup"><span data-stu-id="38f54-328">He also can turn off tracing if he does not want this information to be visible, or he can filter out this information from the trace files after it is logged.</span></span>  
  
 <span data-ttu-id="38f54-329">Являясь частью трассировки ServiceModel, уникальные идентификаторы (называемые идентификаторами действий или, как правило, глобальными уникальными идентификаторами) связывают различные действия друг с другом как поток сообщений, проходящий через разные области инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="38f54-329">As part of ServiceModel Tracing, Unique IDs (called Activity IDs, and typically a GUID) link different activities together as a message flows through different parts of the infrastructure.</span></span>  
  
#### <a name="custom-trace-listeners"></a><span data-ttu-id="38f54-330">Пользовательские прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="38f54-330">Custom Trace Listeners</span></span>  
 <span data-ttu-id="38f54-331">Для ведения журнала сообщений и трассировки можно настроить пользовательский прослушиватель трассировки, который может отправлять трассировки и сообщения по сети (например в удаленную базу данных).</span><span class="sxs-lookup"><span data-stu-id="38f54-331">For both message logging and tracing, a custom trace listener can be configured, which can send traces and messages on the wire (for example, to a remote database).</span></span> <span data-ttu-id="38f54-332">Специалист, выполняющий развертывание приложения, отвечает за настройку пользовательских прослушивателей или разрешение пользователям самостоятельно ее настраивать.</span><span class="sxs-lookup"><span data-stu-id="38f54-332">The application deployer is responsible for configuring custom listeners or enabling users to do so.</span></span> <span data-ttu-id="38f54-333">Он также отвечает за любые персональные данные, раскрытые в удаленном расположении, и за правильное применение элементов управления доступом к этому расположению.</span><span class="sxs-lookup"><span data-stu-id="38f54-333">He is also responsible for any personal information exposed at the remote location, and for properly applying ACLs to this location.</span></span>  
  
### <a name="other-features-for-it-professionals"></a><span data-ttu-id="38f54-334">Другие функции для ИТ-специалистов</span><span class="sxs-lookup"><span data-stu-id="38f54-334">Other features for IT Professionals</span></span>  
 <span data-ttu-id="38f54-335">В WCF имеется поставщик WMI, который предоставляет сведения о конфигурации инфраструктуры WCF через инструментарий WMI (поставляется вместе с Windows).</span><span class="sxs-lookup"><span data-stu-id="38f54-335">WCF has a WMI provider that exposes the WCF infrastructure configuration information through WMI (shipped with Windows).</span></span> <span data-ttu-id="38f54-336">По умолчанию интерфейс WMI доступен для администраторов.</span><span class="sxs-lookup"><span data-stu-id="38f54-336">By default, the WMI interface is available to administrators.</span></span>  
  
 <span data-ttu-id="38f54-337">В конфигурации WCF используется механизм настройки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38f54-337">WCF configuration uses the .NET Framework configuration mechanism.</span></span> <span data-ttu-id="38f54-338">Файлы конфигурации хранятся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="38f54-338">The configuration files are stored on the machine.</span></span> <span data-ttu-id="38f54-339">Разработчик приложения и администратор создают файлы конфигурации и элемент правления доступом для каждого требования приложения.</span><span class="sxs-lookup"><span data-stu-id="38f54-339">The application developer and the administrator create the configuration files and ACL for each of the application's requirements.</span></span> <span data-ttu-id="38f54-340">Файл конфигурации может содержать адреса конечных точек и ссылки на сертификаты в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="38f54-340">A configuration file can contain endpoint addresses and links to certificates in the certificate store.</span></span> <span data-ttu-id="38f54-341">Сертификаты можно использовать, чтобы предоставить данные приложения для настройки различных свойств возможностей, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="38f54-341">The certificates can be used to provide application data to configure various properties of the features used by the application.</span></span>  
  
 <span data-ttu-id="38f54-342">WCF также использует функцию дампа процесса .NET Framework, вызывая метод <xref:System.Environment.FailFast%2A>.</span><span class="sxs-lookup"><span data-stu-id="38f54-342">WCF also uses the .NET Framework process dump functionality by calling the <xref:System.Environment.FailFast%2A> method.</span></span>  
  
### <a name="it-pro-tools"></a><span data-ttu-id="38f54-343">Профессиональные ИТ-средства</span><span class="sxs-lookup"><span data-stu-id="38f54-343">IT Pro Tools</span></span>  
 <span data-ttu-id="38f54-344">WCF также предоставляет следующие средства для ИТ Professional, которые поставляются в Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="38f54-344">WCF also provides the following IT professional tools, which ship in the Windows SDK.</span></span>  
  
#### <a name="svctraceviewerexe"></a><span data-ttu-id="38f54-345">SvcTraceViewer.exe</span><span class="sxs-lookup"><span data-stu-id="38f54-345">SvcTraceViewer.exe</span></span>  
 <span data-ttu-id="38f54-346">В средстве просмотра отображаются файлы трассировки WCF.</span><span class="sxs-lookup"><span data-stu-id="38f54-346">The viewer displays WCF trace files.</span></span> <span data-ttu-id="38f54-347">Средство просмотра позволяет просмотреть информацию, содержащуюся в трассировках.</span><span class="sxs-lookup"><span data-stu-id="38f54-347">The viewer shows whatever information is contained in the traces.</span></span>  
  
#### <a name="svcconfigeditorexe"></a><span data-ttu-id="38f54-348">SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="38f54-348">SvcConfigEditor.exe</span></span>  
 <span data-ttu-id="38f54-349">Редактор позволяет пользователю создавать и изменять файлы конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="38f54-349">The editor allows the user to create and edit WCF configuration files.</span></span> <span data-ttu-id="38f54-350">Редактор показывает всю информацию, содержащуюся в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38f54-350">The editor shows whatever information is contained in the configuration files.</span></span> <span data-ttu-id="38f54-351">Аналогичную задачу можно выполнить с помощью текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="38f54-351">The same task can be accomplished with a text editor.</span></span>  
  
#### <a name="servicemodel_reg"></a><span data-ttu-id="38f54-352">ServiceModel_Reg</span><span class="sxs-lookup"><span data-stu-id="38f54-352">ServiceModel_Reg</span></span>  
 <span data-ttu-id="38f54-353">Это средство позволяет пользователю управлять установкой ServiceModel на компьютере.</span><span class="sxs-lookup"><span data-stu-id="38f54-353">This tool allows the user to manage ServiceModel installs on a machine.</span></span> <span data-ttu-id="38f54-354">Средство отображает сообщения о состоянии в окне консоли при запуске и в процессе может отображать сведения о конфигурации установки WCF.</span><span class="sxs-lookup"><span data-stu-id="38f54-354">The tool displays status messages in a console window when it runs and, in the process, may display information about the configuration of the WCF installation.</span></span>  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a><span data-ttu-id="38f54-355">WSATConfig.exe и WSATUI.dll</span><span class="sxs-lookup"><span data-stu-id="38f54-355">WSATConfig.exe and WSATUI.dll</span></span>  
 <span data-ttu-id="38f54-356">Эти средства позволяют ИТ-специалистам настраивать взаимодействующую сетевую поддержку WS-AtomicTransaction в WCF.</span><span class="sxs-lookup"><span data-stu-id="38f54-356">These tools allow IT Professionals to configure interoperable WS-AtomicTransaction network support in WCF.</span></span> <span data-ttu-id="38f54-357">Средство отображает и позволяет пользователю изменять значения наиболее часто используемых параметров WS-AtomicTransaction, хранящихся в реестре.</span><span class="sxs-lookup"><span data-stu-id="38f54-357">The tools display and allow the user to change the values of the most commonly used WS-AtomicTransaction settings stored in the registry.</span></span>  
  
## <a name="cross-cutting-features"></a><span data-ttu-id="38f54-358">Перекрестные функции</span><span class="sxs-lookup"><span data-stu-id="38f54-358">Cross-cutting Features</span></span>  
 <span data-ttu-id="38f54-359">Следующие функции являются перекрестными.</span><span class="sxs-lookup"><span data-stu-id="38f54-359">The following features are cross-cutting.</span></span> <span data-ttu-id="38f54-360">Это означает, что их можно сочетать с любыми указанными выше функциями.</span><span class="sxs-lookup"><span data-stu-id="38f54-360">That is, they can be composed with any of the preceding features.</span></span>  
  
### <a name="service-framework"></a><span data-ttu-id="38f54-361">Инфраструктура службы</span><span class="sxs-lookup"><span data-stu-id="38f54-361">Service Framework</span></span>  
 <span data-ttu-id="38f54-362">Заголовки могут содержать идентификатор экземпляра, который представляет собой глобальный уникальный идентификатор, связывающий сообщение с экземпляром класса CLR.</span><span class="sxs-lookup"><span data-stu-id="38f54-362">Headers can contain an instance ID, which is a GUID that associates a message with an instance of a CLR class.</span></span>  
  
 <span data-ttu-id="38f54-363">Язык описания веб-служб (WSDL) содержит определение порта.</span><span class="sxs-lookup"><span data-stu-id="38f54-363">The Web Services Description Language (WSDL) contains a definition of the port.</span></span> <span data-ttu-id="38f54-364">У каждого порта имеется адрес конечной точки и привязка, представляющая службы, используемые приложением.</span><span class="sxs-lookup"><span data-stu-id="38f54-364">Each port has an endpoint address and a binding that represents the services used by the application.</span></span> <span data-ttu-id="38f54-365">Предоставление WSDL можно отключить в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38f54-365">Exposing WSDL can be turned off using configuration.</span></span> <span data-ttu-id="38f54-366">Информация на компьютере не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="38f54-366">No information is retained on the machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38f54-367">См. также:</span><span class="sxs-lookup"><span data-stu-id="38f54-367">See also</span></span>

- [<span data-ttu-id="38f54-368">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="38f54-368">Windows Communication Foundation</span></span>](index.md)
- [<span data-ttu-id="38f54-369">Security</span><span class="sxs-lookup"><span data-stu-id="38f54-369">Security</span></span>](./feature-details/security.md)
