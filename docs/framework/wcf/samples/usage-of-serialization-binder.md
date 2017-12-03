---
title: "Использование средства привязки сериализации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e35df7934ffb330feb45e5ff7167c9715f2d291e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="faa89-102">Использование средства привязки сериализации</span><span class="sxs-lookup"><span data-stu-id="faa89-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="faa89-103">В этом образце показано, как использовать <xref:System.Runtime.Serialization.SerializationBinder> для изменения версии универсального типа во время сериализации.</span><span class="sxs-lookup"><span data-stu-id="faa89-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="faa89-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="faa89-104">Demonstrates</span></span>  
 <span data-ttu-id="faa89-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="faa89-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="faa89-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="faa89-106">Discussion</span></span>  
 <span data-ttu-id="faa89-107">Данный образец показывает, как две сущности, ориентированные на разные версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], могут сообщаться с помощью двоичного форматировщика и средства привязки сериализации.</span><span class="sxs-lookup"><span data-stu-id="faa89-107">This sample shows how two entities that are targeting different versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] can communicate using the binary formatter and the serialization binder.</span></span>  
  
 <span data-ttu-id="faa89-108">Разработка данного образца производилась с помощью .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="faa89-108">The development of this sample has been done using .NET Remoting.</span></span> <span data-ttu-id="faa89-109">Образец состоит из сервера, ориентированного на [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], который реализует контракт с универсальными типами, и двух различных клиентов, один из которых ориентирован на [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], а другой на [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="faa89-109">The sample consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="faa89-110">Сервер присоединяет средство привязки <xref:System.Runtime.Serialization.SerializationBinder> к двоичному форматировщику, чтобы иметь возможность соответствующим образом изменять версию типов при сериализации, в результате чего оба клиента смогут правильно десериализовать эти типы.</span><span class="sxs-lookup"><span data-stu-id="faa89-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="faa89-111">Настройка, построение и выполнение примера</span><span class="sxs-lookup"><span data-stu-id="faa89-111">To set up, build and run the sample</span></span>  
  
1.  <span data-ttu-id="faa89-112">Чтобы запустить клиент, щелкните правой кнопкой мыши решение SBGenericsVTS (6 проектов), а затем выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="faa89-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="faa89-113">В **общие свойства**выберите **запускаемый проект**, а затем выберите **несколько запускаемых проектов**.</span><span class="sxs-lookup"><span data-stu-id="faa89-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3.  <span data-ttu-id="faa89-114">Выберите **сервера** первой, затем **Client20** и затем **Client40**.</span><span class="sxs-lookup"><span data-stu-id="faa89-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="faa89-115">Выберите **запустить** для трех этих проектов и оставьте для всего остального значение **нет**.</span><span class="sxs-lookup"><span data-stu-id="faa89-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4.  <span data-ttu-id="faa89-116">Нажмите кнопку **ОК** и нажмите клавишу F5 для запуска примера.</span><span class="sxs-lookup"><span data-stu-id="faa89-116">Click **OK** and then press F5 to run the sample.</span></span>
