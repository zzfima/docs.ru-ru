---
title: Как выполнить Просмотр сертификатов с помощью оснастки MMC
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 72fd6a1be2f33e1bfeb08fd43f3436627ee842e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521586"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="3c4b0-102">Как выполнить Просмотр сертификатов с помощью оснастки MMC</span><span class="sxs-lookup"><span data-stu-id="3c4b0-102">How to: View Certificates with the MMC Snap-in</span></span>
<span data-ttu-id="3c4b0-103">Распространенным типом учетных данных является сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-103">A common type of credential is the X.509 certificate.</span></span> <span data-ttu-id="3c4b0-104">При создании защищенных служб или клиентов задать сертификат для использования в качестве учетных данных клиента или службы можно с помощью таких методов, как <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-104">When creating secure services or clients, you can specify a certificate be used as the client or service credential by using methods such as the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="3c4b0-105">Этот метод требует задания различных параметров, таких как хранилище, в котором находится сертификат, и значение, которое будет использоваться при поиске сертификата.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-105">The method requires various parameters, such as the store where the certificate is stored and a value to use when searching for the certificate.</span></span> <span data-ttu-id="3c4b0-106">В следующей процедуре показано, как просмотреть хранилища на компьютере для поиска соответствующего сертификата.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-106">The following procedure demonstrates how to examine the stores on a computer to find an appropriate certificate.</span></span> <span data-ttu-id="3c4b0-107">Пример поиска отпечатка сертификата, см. в разделе [как: Извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="3c4b0-107">For an example of finding the certificate thumbprint, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="3c4b0-108">Просмотр сертификатов в консоли управления (MMC)</span><span class="sxs-lookup"><span data-stu-id="3c4b0-108">To view certificates in the MMC snap-in</span></span>  
  
1.  <span data-ttu-id="3c4b0-109">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-109">Open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="3c4b0-110">Тип `mmc` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-110">Type `mmc` and press the ENTER key.</span></span> <span data-ttu-id="3c4b0-111">Обратите внимание, что для просмотра сертификатов в хранилище локального компьютера необходимо иметь роль администратора.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-111">Note that to view certificates in the local machine store, you must be in the Administrator role.</span></span>  
  
3.  <span data-ttu-id="3c4b0-112">На **файл** меню, щелкните **Добавить/удалить оснастку**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-112">On the **File** menu, click **Add/Remove Snap In**.</span></span>  
  
4.  <span data-ttu-id="3c4b0-113">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-113">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="3c4b0-114">В **Добавить изолированную оснастку** выберите **сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-114">In the **Add Standalone Snap-in** dialog box, select **Certificates**.</span></span>  
  
6.  <span data-ttu-id="3c4b0-115">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-115">Click **Add**.</span></span>  
  
7.  <span data-ttu-id="3c4b0-116">В **оснастку сертификатов** выберите **учетная запись компьютера** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-116">In the **Certificates snap-in** dialog box, select **Computer account** and click **Next**.</span></span> <span data-ttu-id="3c4b0-117">При необходимости можно выбрать **моей учетной записи пользователя** или **учетной записи службы**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-117">Optionally, you can select **My User account** or **Service account**.</span></span> <span data-ttu-id="3c4b0-118">Если вы не являетесь администратором компьютера, вы можете управлять сертификатами только для своей учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-118">If you are not an administrator of the computer, you can manage certificates only for your user account.</span></span>  
  
8.  <span data-ttu-id="3c4b0-119">В **Выбор компьютера** диалоговом окне щелкните **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-119">In the **Select Computer** dialog box, click **Finish**.</span></span>  
  
9. <span data-ttu-id="3c4b0-120">В **Добавить изолированную оснастку** диалоговом окне щелкните **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-120">In the **Add Standalone Snap-in** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="3c4b0-121">На **Add/Remove Snap-in** диалоговом окне щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-121">On the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="3c4b0-122">В **корень консоли** окно, нажмите кнопку **сертификаты (локальный компьютер)** для просмотра сертификата хранит для компьютера.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-122">In the **Console Root** window, click **Certificates (Local Computer)** to view the certificate stores for the computer.</span></span>  
  
12. <span data-ttu-id="3c4b0-123">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-123">Optional.</span></span> <span data-ttu-id="3c4b0-124">Чтобы просмотреть сертификаты для своей учетной записи, повторите шаги 3 - 6.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-124">To view certificates for your account, repeat steps 3 to 6.</span></span> <span data-ttu-id="3c4b0-125">На шаге 7 вместо пункта **учетная запись компьютера**, нажмите кнопку **моей учетной записи пользователя** и повторите шаги 8 – 10.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-125">In step 7, instead of selecting **Computer account**, click **My User account** and repeat steps 8 to 10.</span></span>  
  
13. <span data-ttu-id="3c4b0-126">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-126">Optional.</span></span> <span data-ttu-id="3c4b0-127">На **файл** меню, щелкните **Сохранить** или **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-127">On the **File** menu, click **Save** or **Save As**.</span></span> <span data-ttu-id="3c4b0-128">Сохраните файл консоли для использования в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-128">Save the console file for later reuse.</span></span>  
  
## <a name="viewing-certificates-with-internet-explorer"></a><span data-ttu-id="3c4b0-129">Просмотр сертификатов с помощью Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="3c4b0-129">Viewing Certificates with Internet Explorer</span></span>  
 <span data-ttu-id="3c4b0-130">Просматривать, экспортировать, импортировать и удалять сертификаты можно также с помощью Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-130">You can also view, export, import, and delete certificates by using Internet Explorer.</span></span>  
  
#### <a name="to-view-certificates-with-internet-explorer"></a><span data-ttu-id="3c4b0-131">Просмотр сертификатов с помощью Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="3c4b0-131">To view certificates with Internet Explorer</span></span>  
  
1.  <span data-ttu-id="3c4b0-132">В Internet Explorer, нажмите кнопку **средства**, затем нажмите кнопку **обозревателя** для отображения **браузера** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-132">In Internet Explorer, click **Tools**, then click **Internet Options** to display the **Internet Options** dialog box.</span></span>  
  
2.  <span data-ttu-id="3c4b0-133">Нажмите кнопку **содержимого** вкладки.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-133">Click the **Content** tab.</span></span>  
  
3.  <span data-ttu-id="3c4b0-134">В разделе **сертификаты**, нажмите кнопку **сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-134">Under **Certificates**, click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="3c4b0-135">Чтобы просмотреть подробные сведения о любой сертификат, выберите сертификат и щелкните **представление**.</span><span class="sxs-lookup"><span data-stu-id="3c4b0-135">To view details of any certificate, select the certificate and click **View**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c4b0-136">См. также</span><span class="sxs-lookup"><span data-stu-id="3c4b0-136">See also</span></span>
- [<span data-ttu-id="3c4b0-137">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="3c4b0-137">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="3c4b0-138">Практическое руководство. Создание временных сертификатов для использования во время разработки</span><span class="sxs-lookup"><span data-stu-id="3c4b0-138">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="3c4b0-139">Практическое руководство. Извлечение отпечатка сертификата</span><span class="sxs-lookup"><span data-stu-id="3c4b0-139">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
