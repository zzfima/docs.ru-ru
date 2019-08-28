---
title: Установка системы очередей сообщений (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 118143f2d434e9f4399c3e9141743fc0254b61ab
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70039622"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="01267-102">Установка системы очередей сообщений (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="01267-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="01267-103">В процедурах ниже показана методика установки очереди сообщений 4.0 и очереди сообщений 3.0.</span><span class="sxs-lookup"><span data-stu-id="01267-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01267-104">Очередь сообщений 4.0 не входит в [!INCLUDE[wxp](../../../../includes/wxp-md.md)] и [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01267-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="01267-105">Установка Message Queuing 4.0 в Windows Server 2008 или Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="01267-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="01267-106">В диспетчер сервера щелкните **компоненты**.</span><span class="sxs-lookup"><span data-stu-id="01267-106">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="01267-107">В области справа в разделе **Сводка компонентов**щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="01267-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="01267-108">В открывшемся окне разверните **очередь сообщений**.</span><span class="sxs-lookup"><span data-stu-id="01267-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="01267-109">Разверните узел **службы очередей сообщений**.</span><span class="sxs-lookup"><span data-stu-id="01267-109">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="01267-110">Щелкните **Интеграция служб каталогов** (для компьютеров, присоединенных к домену), а затем щелкните **Поддержка HTTP**.</span><span class="sxs-lookup"><span data-stu-id="01267-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="01267-111">Нажмите кнопку **Далее**, а затем — **установить**.</span><span class="sxs-lookup"><span data-stu-id="01267-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="01267-112">Установка очереди сообщений 4.0 в Windows 7 или Windows Vista</span><span class="sxs-lookup"><span data-stu-id="01267-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="01267-113">Откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="01267-113">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="01267-114">Щелкните **программы** , а затем в разделе **программы и компоненты**щелкните **Включение и отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="01267-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="01267-115">Разверните сервер очереди сообщений Microsoft (MSMQ), разверните ядро сервера очереди сообщений Microsoft (MSMQ) и затем отметьте флажками установку следующих возможностей очереди сообщений:</span><span class="sxs-lookup"><span data-stu-id="01267-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="01267-116">MSMQ Доменные службы Active Directory (для компьютеров, подключенных к домену).</span><span class="sxs-lookup"><span data-stu-id="01267-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="01267-117">Поддержка MSMQ HTTP.</span><span class="sxs-lookup"><span data-stu-id="01267-117">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="01267-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="01267-118">Click **OK**.</span></span>  
  
5. <span data-ttu-id="01267-119">Если появится запрос на перезагрузку компьютера, нажмите кнопку **ОК** , чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="01267-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="01267-120">Установка Message Queuing 3.0 в Windows XP или Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="01267-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="01267-121">Откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="01267-121">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="01267-122">Щелкните **Добавить удалить программы** , а затем — **Добавить компоненты Windows**.</span><span class="sxs-lookup"><span data-stu-id="01267-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="01267-123">Выберите очередь сообщений и щелкните **сведения**.</span><span class="sxs-lookup"><span data-stu-id="01267-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="01267-124">При работе в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] выберите сервер приложений для доступа к очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="01267-124">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="01267-125">Удостоверьтесь, что на странице сведений выбрана функция поддержки MSMQ HTTP.</span><span class="sxs-lookup"><span data-stu-id="01267-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="01267-126">Нажмите кнопку **ОК** , чтобы закрыть страницу сведения, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="01267-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="01267-127">Завершите установку.</span><span class="sxs-lookup"><span data-stu-id="01267-127">Complete the installation.</span></span>  
  
6. <span data-ttu-id="01267-128">Если появится запрос на перезагрузку компьютера, нажмите кнопку **ОК** , чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="01267-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01267-129">См. также</span><span class="sxs-lookup"><span data-stu-id="01267-129">See also</span></span>

- [<span data-ttu-id="01267-130">Инструкции по настройке</span><span class="sxs-lookup"><span data-stu-id="01267-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)
