---
title: Использование средства привязки сериализации
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 47a1974386927316ea9230ec27cf647d7245c44a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007595"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="1523a-102">Использование средства привязки сериализации</span><span class="sxs-lookup"><span data-stu-id="1523a-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="1523a-103">В этом образце показано, как использовать <xref:System.Runtime.Serialization.SerializationBinder> для изменения версии универсального типа во время сериализации.</span><span class="sxs-lookup"><span data-stu-id="1523a-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="1523a-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="1523a-104">Demonstrates</span></span>  
 <span data-ttu-id="1523a-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="1523a-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="1523a-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="1523a-106">Discussion</span></span>  
 <span data-ttu-id="1523a-107">Данный образец показывает, как две сущности, ориентированные на разные версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], могут сообщаться с помощью двоичного форматировщика и средства привязки сериализации.</span><span class="sxs-lookup"><span data-stu-id="1523a-107">This sample shows how two entities that are targeting different versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] can communicate using the binary formatter and the serialization binder.</span></span>  
  
 <span data-ttu-id="1523a-108">Разработка данного образца производилась с помощью .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="1523a-108">The development of this sample has been done using .NET Remoting.</span></span> <span data-ttu-id="1523a-109">Образец состоит из сервера, ориентированного на [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], который реализует контракт с универсальными типами, и двух различных клиентов, один из которых ориентирован на [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], а другой на [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1523a-109">The sample consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="1523a-110">Сервер присоединяет средство привязки <xref:System.Runtime.Serialization.SerializationBinder> к двоичному форматировщику, чтобы иметь возможность соответствующим образом изменять версию типов при сериализации, в результате чего оба клиента смогут правильно десериализовать эти типы.</span><span class="sxs-lookup"><span data-stu-id="1523a-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1523a-111">Настройка, построение и выполнение примера</span><span class="sxs-lookup"><span data-stu-id="1523a-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="1523a-112">Чтобы запустить клиент, щелкните правой кнопкой мыши решение SBGenericsVTS (6 проектов), а затем выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="1523a-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="1523a-113">В **общие свойства**выберите **запускаемым проектом**, а затем выберите **несколько запускаемых проектов**.</span><span class="sxs-lookup"><span data-stu-id="1523a-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="1523a-114">Выберите **Server** первой, затем **Client20** и затем **Client40**.</span><span class="sxs-lookup"><span data-stu-id="1523a-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="1523a-115">Выберите **запустить** действие для трех этих проектов и оставьте остальные **None**.</span><span class="sxs-lookup"><span data-stu-id="1523a-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="1523a-116">Нажмите кнопку **ОК** и нажмите клавишу F5 для запуска примера.</span><span class="sxs-lookup"><span data-stu-id="1523a-116">Click **OK** and then press F5 to run the sample.</span></span>
