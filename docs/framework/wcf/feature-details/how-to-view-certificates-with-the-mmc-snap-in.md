---
title: Как посмотреть сертификаты с MMC snap-in
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184786"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="214cd-102">Как посмотреть сертификаты с MMC snap-in</span><span class="sxs-lookup"><span data-stu-id="214cd-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="214cd-103">При создании безопасного клиента или службы вы можете использовать [сертификат](working-with-certificates.md) в качестве учетных данных.</span><span class="sxs-lookup"><span data-stu-id="214cd-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="214cd-104">Например, общим типом учетных данных является сертификат X.509, который вы создаете с помощью метода. <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="214cd-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="214cd-105">Существует три различных типа сертификатов, которые можно изучить с помощью консоли управления Майкрософт (MMC) в системах Windows:</span><span class="sxs-lookup"><span data-stu-id="214cd-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="214cd-106">Локальный компьютер: Магазин является локальным для устройства и глобальным для всех пользователей на устройстве.</span><span class="sxs-lookup"><span data-stu-id="214cd-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="214cd-107">Текущий пользователь: Хранилище локально к текущей учетной записи пользователя на устройстве.</span><span class="sxs-lookup"><span data-stu-id="214cd-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="214cd-108">Учетная запись обслуживания: Магазин является локальным для конкретной службы на устройстве.</span><span class="sxs-lookup"><span data-stu-id="214cd-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="214cd-109">Просмотр сертификатов в MMC snap-in</span><span class="sxs-lookup"><span data-stu-id="214cd-109">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="214cd-110">Следующая процедура демонстрирует, как изучить магазины на локальном устройстве, чтобы найти соответствующий сертификат:</span><span class="sxs-lookup"><span data-stu-id="214cd-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="214cd-111">Выберите **Выполнить** из меню **Пуск,** а затем введите *mmc*.</span><span class="sxs-lookup"><span data-stu-id="214cd-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="214cd-112">Появляется MMC.</span><span class="sxs-lookup"><span data-stu-id="214cd-112">The MMC appears.</span></span>
  
2. <span data-ttu-id="214cd-113">Из меню **файла** выберите **Добавить/Удалить Snap In**.</span><span class="sxs-lookup"><span data-stu-id="214cd-113">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="214cd-114">Отображается окно **Добавить или удалить привязки.**</span><span class="sxs-lookup"><span data-stu-id="214cd-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="214cd-115">Из **списка доступных свай-вс** выберите **Сертификаты,** а затем **выберите Добавить.**</span><span class="sxs-lookup"><span data-stu-id="214cd-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Добавление сертификата оснастки в](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="214cd-117">В окне **защелки Сертификатов** выберите **учетную запись компьютера,** а затем выберите **Следующий.**</span><span class="sxs-lookup"><span data-stu-id="214cd-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="214cd-118">В желании можно выбрать **учетную запись "Мой пользователь"** для текущей **учетной записи** пользователя или службы для конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="214cd-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="214cd-119">Если вы не являетесь администратором устройства, вы можете управлять сертификатами только для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="214cd-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="214cd-120">В окне **компьютера Select** выможете выбрать **выбранный локальный компьютер,** а затем выберите **Finish.**</span><span class="sxs-lookup"><span data-stu-id="214cd-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="214cd-121">В окне **добавить или удалить Snap-in** выберите **OK**.</span><span class="sxs-lookup"><span data-stu-id="214cd-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Добавление сертификата оснастки в](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="214cd-123">Дополнительно: Из меню **файла** выберите **Сохранить** или **сохранить Как** сохранить файл консоли MMC для последующего использования.</span><span class="sxs-lookup"><span data-stu-id="214cd-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="214cd-124">Для просмотра сертификатов в MMC snap-in выберите **консоль Root** в левом стекле, а затем расширьте **Сертификаты (местный компьютер).**</span><span class="sxs-lookup"><span data-stu-id="214cd-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="214cd-125">Отображается список каталогов для каждого типа сертификата.</span><span class="sxs-lookup"><span data-stu-id="214cd-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="214cd-126">Из каждого каталога сертификатов можно просматривать, экспортировать, импортировать и удалять его сертификаты.</span><span class="sxs-lookup"><span data-stu-id="214cd-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="214cd-127">Просмотр сертификатов с помощью инструмента «Менеджер сертификата»</span><span class="sxs-lookup"><span data-stu-id="214cd-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="214cd-128">Вы также можете просматривать, экспортировать, импортировать и удалять сертификаты с помощью инструмента «Менеджер сертификатов».</span><span class="sxs-lookup"><span data-stu-id="214cd-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="214cd-129">Просмотр сертификатов для локального устройства</span><span class="sxs-lookup"><span data-stu-id="214cd-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="214cd-130">Выберите **Выполнить** из меню **Пуск,** а затем ввести *certlm.msc*.</span><span class="sxs-lookup"><span data-stu-id="214cd-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="214cd-131">Появляется инструмент manager сертификата для локального устройства.</span><span class="sxs-lookup"><span data-stu-id="214cd-131">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="214cd-132">Чтобы просмотреть сертификаты, в соответствии с **сертификатами - Локальный компьютер** в левом стеку, расширьте каталог для типа сертификата, который вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="214cd-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="214cd-133">Просмотр сертификатов для текущего пользователя</span><span class="sxs-lookup"><span data-stu-id="214cd-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="214cd-134">Выберите **Выполнить** из меню **Пуск,** а затем ввести *certmgr.msc*.</span><span class="sxs-lookup"><span data-stu-id="214cd-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="214cd-135">Отображается инструмент manager сертификата для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="214cd-135">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="214cd-136">Чтобы просмотреть сертификаты, в соответствии с **сертификатами - Текущий пользователь** в левом стеку, расширьте каталог для типа сертификата, который вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="214cd-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="214cd-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="214cd-137">See also</span></span>

- [<span data-ttu-id="214cd-138">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="214cd-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="214cd-139">Как: Создание временных сертификатов для использования во время разработки</span><span class="sxs-lookup"><span data-stu-id="214cd-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="214cd-140">Как: Получить отпечаток пальца сертификата</span><span class="sxs-lookup"><span data-stu-id="214cd-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
