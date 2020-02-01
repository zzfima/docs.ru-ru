---
title: Установка системы очередей сообщений (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 8ecbd07adfb6bfb4e9898f9b8508809480d17e16
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921104"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="7209a-102">Установка системы очередей сообщений (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="7209a-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="7209a-103">В процедурах ниже показана методика установки очереди сообщений 4.0 и очереди сообщений 3.0.</span><span class="sxs-lookup"><span data-stu-id="7209a-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7209a-104">Служба очереди сообщений 4,0 недоступна в Windows XP и Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="7209a-104">Message Queuing 4.0 is not available in Windows XP and Windows Server 2003.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="7209a-105">Установка Message Queuing 4.0 в Windows Server 2008 или Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7209a-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="7209a-106">В диспетчер сервера щелкните **компоненты**.</span><span class="sxs-lookup"><span data-stu-id="7209a-106">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="7209a-107">В области справа в разделе **Сводка компонентов**щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="7209a-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="7209a-108">В открывшемся окне разверните **очередь сообщений**.</span><span class="sxs-lookup"><span data-stu-id="7209a-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="7209a-109">Разверните узел **службы очередей сообщений**.</span><span class="sxs-lookup"><span data-stu-id="7209a-109">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="7209a-110">Щелкните **Интеграция служб каталогов** (для компьютеров, присоединенных к домену), а затем щелкните **Поддержка HTTP**.</span><span class="sxs-lookup"><span data-stu-id="7209a-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="7209a-111">Нажмите кнопку **Далее**, а затем — **установить**.</span><span class="sxs-lookup"><span data-stu-id="7209a-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="7209a-112">Установка очереди сообщений 4.0 в Windows 7 или Windows Vista</span><span class="sxs-lookup"><span data-stu-id="7209a-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="7209a-113">Откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="7209a-113">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="7209a-114">Щелкните **программы** , а затем в разделе **программы и компоненты**щелкните **Включение и отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="7209a-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="7209a-115">Разверните узел Сервер службы очередей сообщений Windows (MSMQ), разверните узел Базовые возможности сервера службы очередей сообщенийMicrosoft (MSMQ) и установите флажки рядом со следующими устанавливаемыми возможностями службы очередей сообщений.</span><span class="sxs-lookup"><span data-stu-id="7209a-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="7209a-116">MSMQ Доменные службы Active Directory (для компьютеров, подключенных к домену).</span><span class="sxs-lookup"><span data-stu-id="7209a-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="7209a-117">Поддержка MSMQ HTTP.</span><span class="sxs-lookup"><span data-stu-id="7209a-117">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="7209a-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7209a-118">Click **OK**.</span></span>  
  
5. <span data-ttu-id="7209a-119">Если появится запрос на перезагрузку компьютера, нажмите кнопку **ОК** , чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="7209a-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="7209a-120">Установка Message Queuing 3.0 в Windows XP или Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="7209a-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="7209a-121">Откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="7209a-121">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="7209a-122">Щелкните **Добавить удалить программы** , а затем — **Добавить компоненты Windows**.</span><span class="sxs-lookup"><span data-stu-id="7209a-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="7209a-123">Выберите очередь сообщений и щелкните **сведения**.</span><span class="sxs-lookup"><span data-stu-id="7209a-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7209a-124">Если вы используете Windows Server 2003, выберите сервер приложений для доступа к очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="7209a-124">If you are running Windows Server 2003, select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="7209a-125">Удостоверьтесь, что на странице сведений выбрана функция поддержки MSMQ HTTP.</span><span class="sxs-lookup"><span data-stu-id="7209a-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="7209a-126">Нажмите кнопку **ОК** , чтобы закрыть страницу сведения, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7209a-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="7209a-127">Завершите установку.</span><span class="sxs-lookup"><span data-stu-id="7209a-127">Complete the installation.</span></span>  
  
6. <span data-ttu-id="7209a-128">Если появится запрос на перезагрузку компьютера, нажмите кнопку **ОК** , чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="7209a-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7209a-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="7209a-129">See also</span></span>

- [<span data-ttu-id="7209a-130">Инструкции по настройке</span><span class="sxs-lookup"><span data-stu-id="7209a-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)
