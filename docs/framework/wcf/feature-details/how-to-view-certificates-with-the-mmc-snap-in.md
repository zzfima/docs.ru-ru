---
title: "Практическое руководство. Просмотр сертификатов с помощью оснастки консоли MMC"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 582eaef518e10acb4c4c356226ce0be24d1b4c35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="1b429-102">Практическое руководство. Просмотр сертификатов с помощью оснастки консоли MMC</span><span class="sxs-lookup"><span data-stu-id="1b429-102">How to: View Certificates with the MMC Snap-in</span></span>
<span data-ttu-id="1b429-103">Распространенным типом учетных данных является сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="1b429-103">A common type of credential is the X.509 certificate.</span></span> <span data-ttu-id="1b429-104">При создании защищенных служб или клиентов задать сертификат для использования в качестве учетных данных клиента или службы можно с помощью таких методов, как <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="1b429-104">When creating secure services or clients, you can specify a certificate be used as the client or service credential by using methods such as the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="1b429-105">Этот метод требует задания различных параметров, таких как хранилище, в котором находится сертификат, и значение, которое будет использоваться при поиске сертификата.</span><span class="sxs-lookup"><span data-stu-id="1b429-105">The method requires various parameters, such as the store where the certificate is stored and a value to use when searching for the certificate.</span></span> <span data-ttu-id="1b429-106">В следующей процедуре показано, как просмотреть хранилища на компьютере для поиска соответствующего сертификата.</span><span class="sxs-lookup"><span data-stu-id="1b429-106">The following procedure demonstrates how to examine the stores on a computer to find an appropriate certificate.</span></span> <span data-ttu-id="1b429-107">Пример поиска отпечаток сертификата см. в разделе [как: извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="1b429-107">For an example of finding the certificate thumbprint, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="1b429-108">Просмотр сертификатов в консоли управления (MMC)</span><span class="sxs-lookup"><span data-stu-id="1b429-108">To view certificates in the MMC snap-in</span></span>  
  
1.  <span data-ttu-id="1b429-109">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="1b429-109">Open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="1b429-110">Тип `mmc` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1b429-110">Type `mmc` and press the ENTER key.</span></span> <span data-ttu-id="1b429-111">Обратите внимание, что для просмотра сертификатов в хранилище локального компьютера необходимо иметь роль администратора.</span><span class="sxs-lookup"><span data-stu-id="1b429-111">Note that to view certificates in the local machine store, you must be in the Administrator role.</span></span>  
  
3.  <span data-ttu-id="1b429-112">На **файл** меню, нажмите кнопку **добавить или удалить оснастку**.</span><span class="sxs-lookup"><span data-stu-id="1b429-112">On the **File** menu, click **Add/Remove Snap In**.</span></span>  
  
4.  <span data-ttu-id="1b429-113">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1b429-113">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="1b429-114">В **Добавить изолированную оснастку** выберите **сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="1b429-114">In the **Add Standalone Snap-in** dialog box, select **Certificates**.</span></span>  
  
6.  <span data-ttu-id="1b429-115">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1b429-115">Click **Add**.</span></span>  
  
7.  <span data-ttu-id="1b429-116">В **оснастку сертификатов** выберите **учетная запись компьютера** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1b429-116">In the **Certificates snap-in** dialog box, select **Computer account** and click **Next**.</span></span> <span data-ttu-id="1b429-117">При необходимости можно выбрать **Моя учетная запись пользователя** или **учетной записи службы**.</span><span class="sxs-lookup"><span data-stu-id="1b429-117">Optionally, you can select **My User account** or **Service account**.</span></span> <span data-ttu-id="1b429-118">Если вы не являетесь администратором компьютера, вы можете управлять сертификатами только для своей учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="1b429-118">If you are not an administrator of the computer, you can manage certificates only for your user account.</span></span>  
  
8.  <span data-ttu-id="1b429-119">В **Выбор компьютера** диалоговое окно, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="1b429-119">In the **Select Computer** dialog box, click **Finish**.</span></span>  
  
9. <span data-ttu-id="1b429-120">В **Добавить изолированную оснастку** диалоговое окно, нажмите кнопку **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1b429-120">In the **Add Standalone Snap-in** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="1b429-121">На **добавить или удалить оснастку** диалоговое окно, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1b429-121">On the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="1b429-122">В **корень консоли** окно, нажмите кнопку **сертификаты (локальный компьютер)** для просмотра сертификата хранятся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1b429-122">In the **Console Root** window, click **Certificates (Local Computer)** to view the certificate stores for the computer.</span></span>  
  
12. <span data-ttu-id="1b429-123">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="1b429-123">Optional.</span></span> <span data-ttu-id="1b429-124">Чтобы просмотреть сертификаты для своей учетной записи, повторите шаги 3 - 6.</span><span class="sxs-lookup"><span data-stu-id="1b429-124">To view certificates for your account, repeat steps 3 to 6.</span></span> <span data-ttu-id="1b429-125">В шаге 7 вместо пункта **учетная запись компьютера**, нажмите кнопку **Моя учетная запись пользователя** и повторите шаги 8 – 10.</span><span class="sxs-lookup"><span data-stu-id="1b429-125">In step 7, instead of selecting **Computer account**, click **My User account** and repeat steps 8 to 10.</span></span>  
  
13. <span data-ttu-id="1b429-126">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="1b429-126">Optional.</span></span> <span data-ttu-id="1b429-127">На **файл** меню, нажмите кнопку **Сохранить** или **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="1b429-127">On the **File** menu, click **Save** or **Save As**.</span></span> <span data-ttu-id="1b429-128">Сохраните файл консоли для использования в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="1b429-128">Save the console file for later reuse.</span></span>  
  
## <a name="viewing-certificates-with-internet-explorer"></a><span data-ttu-id="1b429-129">Просмотр сертификатов с помощью Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="1b429-129">Viewing Certificates with Internet Explorer</span></span>  
 <span data-ttu-id="1b429-130">Просматривать, экспортировать, импортировать и удалять сертификаты можно также с помощью Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="1b429-130">You can also view, export, import, and delete certificates by using Internet Explorer.</span></span>  
  
#### <a name="to-view-certificates-with-internet-explorer"></a><span data-ttu-id="1b429-131">Просмотр сертификатов с помощью Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="1b429-131">To view certificates with Internet Explorer</span></span>  
  
1.  <span data-ttu-id="1b429-132">В Internet Explorer, нажмите кнопку **средства**, нажмите кнопку **обозревателя** для отображения **обозревателя** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="1b429-132">In Internet Explorer, click **Tools**, then click **Internet Options** to display the **Internet Options** dialog box.</span></span>  
  
2.  <span data-ttu-id="1b429-133">Нажмите кнопку **содержимого** вкладки.</span><span class="sxs-lookup"><span data-stu-id="1b429-133">Click the **Content** tab.</span></span>  
  
3.  <span data-ttu-id="1b429-134">В разделе **сертификаты**, нажмите кнопку **сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="1b429-134">Under **Certificates**, click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="1b429-135">Чтобы просмотреть подробные сведения о любой сертификат, выберите сертификат и нажмите кнопку **представление**.</span><span class="sxs-lookup"><span data-stu-id="1b429-135">To view details of any certificate, select the certificate and click **View**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b429-136">См. также</span><span class="sxs-lookup"><span data-stu-id="1b429-136">See Also</span></span>  
 [<span data-ttu-id="1b429-137">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="1b429-137">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="1b429-138">Практическое руководство. Создание временных сертификатов для использования во время разработки</span><span class="sxs-lookup"><span data-stu-id="1b429-138">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)  
 [<span data-ttu-id="1b429-139">Практическое руководство. Извлечение отпечатка сертификата</span><span class="sxs-lookup"><span data-stu-id="1b429-139">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
