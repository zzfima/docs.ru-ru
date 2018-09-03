---
title: Кодировщик ByteStream
ms.date: 03/30/2017
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
ms.openlocfilehash: cbd4110ecc04923b79d6b910fcf7ab4ca2012680
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480696"
---
# <a name="bytestream-encoder"></a><span data-ttu-id="e3af4-102">Кодировщик ByteStream</span><span class="sxs-lookup"><span data-stu-id="e3af4-102">ByteStream Encoder</span></span>
<span data-ttu-id="e3af4-103">В этом образце показано, как создать привязку `ByteStreamHttpBinding`, которая имеет тип <xref:System.ServiceModel.Channels.Binding> и демонстрирует функциональные возможности кодировщика байтового потока.</span><span class="sxs-lookup"><span data-stu-id="e3af4-103">This sample demonstrates how to create a `ByteStreamHttpBinding`, a <xref:System.ServiceModel.Channels.Binding> that demonstrates the functionality of the byte stream encoder.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="e3af4-104">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="e3af4-104">Discussion</span></span>  
 <span data-ttu-id="e3af4-105">В этом образце показано, как создать стандартную привязку <xref:System.ServiceModel.Channels.Binding> с использованием стандартных элементов привязки <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> и <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="e3af4-105">This sample demonstrates how to create a standard <xref:System.ServiceModel.Channels.Binding> using the standard binding elements <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span> <span data-ttu-id="e3af4-106">В этом образце показано, как использовать кодировщик байтового потока для передачи и загрузки изображения.</span><span class="sxs-lookup"><span data-stu-id="e3af4-106">This sample shows how to use the byte stream encoder to upload and download an image.</span></span> <span data-ttu-id="e3af4-107">Функция кодировщика байтового потока поддерживает только транспорт HTTP и не поддерживает такие функции, как надежный обмен сообщениями и безопасность.</span><span class="sxs-lookup"><span data-stu-id="e3af4-107">The byte stream encoder feature only supports the HTTP transport and it does not support features such as reliable messaging or security.</span></span> <span data-ttu-id="e3af4-108">Для <xref:System.ServiceModel.Channels.MessageVersion> поддерживается только значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3af4-108">The only <xref:System.ServiceModel.Channels.MessageVersion> supported is <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3af4-109">Если этот образец работает в [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] или [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], убедитесь, что среда [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] запущена с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="e3af4-109">If you are running this sample in [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] or [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], ensure that you are running [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with elevated privileges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3af4-110">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3af4-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e3af4-111">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e3af4-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e3af4-112">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="e3af4-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e3af4-113">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e3af4-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e3af4-114">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e3af4-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e3af4-115">Откройте файл ByteStreamHttpBinding.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3af4-115">Open the ByteStreamHttpBinding.sln file in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3af4-116">Запустите новый экземпляр проекта ByteStreamHttpBindingServer, щелкнув правой кнопкой мыши проект в обозревателе решений и выбрав **Отладка**, а затем **запустить новый экземпляр** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="e3af4-116">Start a new instance of the ByteStreamHttpBindingServer project by right-clicking the project in the Solution Explorer and selecting **Debug**, and then **Start new instance** from the context menu.</span></span>  
  
3.  <span data-ttu-id="e3af4-117">Запустите новый экземпляр проекта ByteStreamHttpBindingClient, щелкнув правой кнопкой мыши проект в обозревателе решений и выбрав **Отладка**, **запустить новый экземпляр** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="e3af4-117">Start a new instance of the ByteStreamHttpBindingClient project by right-clicking the project in the Solution Explorer and selecting **Debug**, **Start new instance** from the context menu.</span></span>
