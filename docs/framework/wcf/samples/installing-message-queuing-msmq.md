---
title: Установка системы очередей сообщений (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 2aae92ba6e373af2d8bc9cff0b4c9d317ba10136
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588029"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="a8432-102">Установка системы очередей сообщений (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="a8432-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="a8432-103">В процедурах ниже показана методика установки очереди сообщений 4.0 и очереди сообщений 3.0.</span><span class="sxs-lookup"><span data-stu-id="a8432-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8432-104">Очередь сообщений 4.0 не входит в [!INCLUDE[wxp](../../../../includes/wxp-md.md)] и [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8432-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="a8432-105">Установка Message Queuing 4.0 в Windows Server 2008 или Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a8432-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="a8432-106">В диспетчере серверов щелкните **функции**.</span><span class="sxs-lookup"><span data-stu-id="a8432-106">In Server Manager, click **Features**.</span></span>  
  
2.  <span data-ttu-id="a8432-107">На панели справа в разделе **ׁגמהךא**, нажмите кнопку **добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="a8432-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3.  <span data-ttu-id="a8432-108">В появившемся окне разверните **Message Queuing**.</span><span class="sxs-lookup"><span data-stu-id="a8432-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4.  <span data-ttu-id="a8432-109">Разверните **службы очереди сообщений**.</span><span class="sxs-lookup"><span data-stu-id="a8432-109">Expand **Message Queuing Services**.</span></span>  
  
5.  <span data-ttu-id="a8432-110">Нажмите кнопку **интеграция со службами каталогов** (для компьютеров, присоединенных к домену), а затем нажмите кнопку **поддержка HTTP**.</span><span class="sxs-lookup"><span data-stu-id="a8432-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6.  <span data-ttu-id="a8432-111">Нажмите кнопку **Далее**, затем нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="a8432-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="a8432-112">Установка очереди сообщений 4.0 в Windows 7 или Windows Vista</span><span class="sxs-lookup"><span data-stu-id="a8432-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1.  <span data-ttu-id="a8432-113">Откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="a8432-113">Open **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="a8432-114">Нажмите кнопку **программы** и затем в разделе **программы и компоненты**, нажмите кнопку **Включение и отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="a8432-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3.  <span data-ttu-id="a8432-115">Разверните сервер очереди сообщений Microsoft (MSMQ), разверните ядро сервера очереди сообщений Microsoft (MSMQ) и затем отметьте флажками установку следующих возможностей очереди сообщений:</span><span class="sxs-lookup"><span data-stu-id="a8432-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    -   <span data-ttu-id="a8432-116">MSMQ Доменные службы Active Directory (для компьютеров, подключенных к домену).</span><span class="sxs-lookup"><span data-stu-id="a8432-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    -   <span data-ttu-id="a8432-117">Поддержка MSMQ HTTP.</span><span class="sxs-lookup"><span data-stu-id="a8432-117">MSMQ HTTP Support.</span></span>  
  
4.  <span data-ttu-id="a8432-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8432-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a8432-119">При появлении запроса на перезагрузку компьютера нажмите кнопку **ОК** для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="a8432-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="a8432-120">Установка Message Queuing 3.0 в Windows XP или Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="a8432-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1.  <span data-ttu-id="a8432-121">Откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="a8432-121">Open **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="a8432-122">Нажмите кнопку **Установка и удаление программ** и нажмите кнопку **Добавление компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="a8432-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3.  <span data-ttu-id="a8432-123">Выберите очереди сообщений и нажмите кнопку **сведения**.</span><span class="sxs-lookup"><span data-stu-id="a8432-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a8432-124">При работе в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] выберите сервер приложений для доступа к очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="a8432-124">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], select Application Server to access Message Queuing.</span></span>  
  
4.  <span data-ttu-id="a8432-125">Удостоверьтесь, что на странице сведений выбрана функция поддержки MSMQ HTTP.</span><span class="sxs-lookup"><span data-stu-id="a8432-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5.  <span data-ttu-id="a8432-126">Нажмите кнопку **ОК** закрыть страницу сведений, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a8432-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="a8432-127">Завершите установку.</span><span class="sxs-lookup"><span data-stu-id="a8432-127">Complete the installation.</span></span>  
  
6.  <span data-ttu-id="a8432-128">При появлении запроса на перезагрузку компьютера нажмите кнопку **ОК** для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="a8432-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8432-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a8432-129">See also</span></span>
- [<span data-ttu-id="a8432-130">Инструкции по настройке</span><span class="sxs-lookup"><span data-stu-id="a8432-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)
