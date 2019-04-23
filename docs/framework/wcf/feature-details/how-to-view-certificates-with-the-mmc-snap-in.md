---
title: Практическое руководство. Просмотр сертификатов с помощью оснастки MMC
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 69f79b64250ff46524e7b4720d13351774875a3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167509"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="729e1-102">Практическое руководство. Просмотр сертификатов с помощью оснастки MMC</span><span class="sxs-lookup"><span data-stu-id="729e1-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="729e1-103">При создании безопасного клиента или службы, можно использовать [сертификат](working-with-certificates.md) как учетные данные.</span><span class="sxs-lookup"><span data-stu-id="729e1-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="729e1-104">Например, тип учетных данных является сертификат X.509, который вы создадите с <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="729e1-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span> 

<span data-ttu-id="729e1-105">Существует три типа хранилища сертификатов, которые можно проверить с помощью консоли управления (MMC) в системах Windows.</span><span class="sxs-lookup"><span data-stu-id="729e1-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="729e1-106">Локальный компьютер: Хранилище является локальным для устройства и общий для всех пользователей на устройстве.</span><span class="sxs-lookup"><span data-stu-id="729e1-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="729e1-107">Текущий пользователь: Хранилище является локальной для текущей учетной записи пользователя на устройстве.</span><span class="sxs-lookup"><span data-stu-id="729e1-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="729e1-108">Учетная запись службы: Хранилище является локальной для определенной службы на устройстве.</span><span class="sxs-lookup"><span data-stu-id="729e1-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="729e1-109">Просмотр сертификатов в оснастке MMC</span><span class="sxs-lookup"><span data-stu-id="729e1-109">View certificates in the MMC snap-in</span></span> 

<span data-ttu-id="729e1-110">Ниже показано, как просмотреть хранилища на локальном устройстве, чтобы найти соответствующий сертификат:</span><span class="sxs-lookup"><span data-stu-id="729e1-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span> 
  
1. <span data-ttu-id="729e1-111">Выберите **запуска** из **запустить** меню, а затем введите *mmc*.</span><span class="sxs-lookup"><span data-stu-id="729e1-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span> 

    <span data-ttu-id="729e1-112">Откроется консоль Управления.</span><span class="sxs-lookup"><span data-stu-id="729e1-112">The MMC appears.</span></span> 
  
2. <span data-ttu-id="729e1-113">Из **файл** меню, выберите **Добавить/удалить оснастку**.</span><span class="sxs-lookup"><span data-stu-id="729e1-113">From the **File** menu, select **Add/Remove Snap In**.</span></span> 
    
    <span data-ttu-id="729e1-114">**Добавление или удаление оснасток** появится окно.</span><span class="sxs-lookup"><span data-stu-id="729e1-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="729e1-115">Из **Доступные оснастки** выберите **сертификаты**, а затем выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="729e1-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Добавление оснастки диспетчера сертификатов](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="729e1-117">В **оснастку сертификатов** выберите **учетная запись компьютера**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="729e1-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span> 
  
    <span data-ttu-id="729e1-118">При необходимости можно выбрать **моей учетной записи пользователя** для текущего пользователя или **учетной записи службы** для конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="729e1-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="729e1-119">Если вы не являетесь администратором для устройства, вы можете управлять сертификатами только для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="729e1-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="729e1-120">В **Выбор компьютера** окне оставьте **локального компьютера** выбран, а затем выберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="729e1-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="729e1-121">В **добавить или удалить оснастку** выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="729e1-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Добавление оснастки диспетчера сертификатов](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="729e1-123">Необязательные: Из **файл** меню, выберите **Сохранить** или **Сохранить как** для сохранения файла консоли MMC для последующего использования.</span><span class="sxs-lookup"><span data-stu-id="729e1-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="729e1-124">Чтобы просмотреть сертификаты в оснастке MMC, выберите **корень консоли** в левой панели раскройте **сертификаты (локальный компьютер)**.</span><span class="sxs-lookup"><span data-stu-id="729e1-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="729e1-125">Появится список каталогов для каждого типа сертификата.</span><span class="sxs-lookup"><span data-stu-id="729e1-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="729e1-126">Из каталога каждого сертификата можно просматривать, экспортировать, импортировать и удалите свои сертификаты.</span><span class="sxs-lookup"><span data-stu-id="729e1-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="729e1-127">Просмотр сертификатов с помощью средство диспетчера сертификатов</span><span class="sxs-lookup"><span data-stu-id="729e1-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="729e1-128">Можно также просматривать, экспортировать, импортировать и удалить сертификаты, используя средство диспетчера сертификатов.</span><span class="sxs-lookup"><span data-stu-id="729e1-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="729e1-129">Чтобы просмотреть сертификаты для локальных устройств</span><span class="sxs-lookup"><span data-stu-id="729e1-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="729e1-130">Выберите **запуска** из **запустить** меню, а затем введите *certlm.msc*.</span><span class="sxs-lookup"><span data-stu-id="729e1-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span> 

    <span data-ttu-id="729e1-131">Появится средство диспетчера сертификатов для локальных устройств.</span><span class="sxs-lookup"><span data-stu-id="729e1-131">The Certificate Manager tool for the local device appears.</span></span> 
  
2. <span data-ttu-id="729e1-132">Чтобы просмотреть сертификаты, в разделе **сертификаты — локальный компьютер** в области слева разверните каталог для типа сертификата, вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="729e1-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="729e1-133">Чтобы просмотреть сертификаты для текущего пользователя</span><span class="sxs-lookup"><span data-stu-id="729e1-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="729e1-134">Выберите **запуска** из **запустить** меню, а затем введите *certmgr.msc*.</span><span class="sxs-lookup"><span data-stu-id="729e1-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span> 

    <span data-ttu-id="729e1-135">Появится средство диспетчера сертификатов для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="729e1-135">The Certificate Manager tool for the current user appears.</span></span> 
  
2. <span data-ttu-id="729e1-136">Чтобы просмотреть сертификаты, в разделе **Сертификаты — текущий пользователь** в области слева разверните каталог для типа сертификата, вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="729e1-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="729e1-137">См. также</span><span class="sxs-lookup"><span data-stu-id="729e1-137">See also</span></span>

- [<span data-ttu-id="729e1-138">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="729e1-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="729e1-139">Практическое руководство. Создание временных сертификатов для использования во время разработки</span><span class="sxs-lookup"><span data-stu-id="729e1-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="729e1-140">Практическое руководство. Извлечение отпечатка сертификата</span><span class="sxs-lookup"><span data-stu-id="729e1-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
