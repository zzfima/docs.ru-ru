---
title: Использование средства привязки сериализации
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 10900950b935b484053fe8e37263f0dfc25eba99
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348459"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="a2162-102">Использование средства привязки сериализации</span><span class="sxs-lookup"><span data-stu-id="a2162-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="a2162-103">В этом образце показано, как использовать <xref:System.Runtime.Serialization.SerializationBinder> для изменения версии универсального типа во время сериализации.</span><span class="sxs-lookup"><span data-stu-id="a2162-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="a2162-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="a2162-104">Demonstrates</span></span>  
 <span data-ttu-id="a2162-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="a2162-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="a2162-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="a2162-106">Discussion</span></span>  
 <span data-ttu-id="a2162-107">В этом примере показано, как две сущности, предназначенных для разных версий .NET Framework могут обмениваться данными с помощью двоичного форматировщика и средства привязки сериализации.</span><span class="sxs-lookup"><span data-stu-id="a2162-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="a2162-108">Этот образец разработан с использованием удаленного взаимодействия .NET.</span><span class="sxs-lookup"><span data-stu-id="a2162-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="a2162-109">Он состоит из сервера, ориентированного [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], который реализует контракт с универсальными типами и двух различных клиентов, один выбора целевой платформы .NET Framework 2.0 и другой на [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2162-109">It consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="a2162-110">Сервер присоединяет средство привязки <xref:System.Runtime.Serialization.SerializationBinder> к двоичному форматировщику, чтобы иметь возможность соответствующим образом изменять версию типов при сериализации, в результате чего оба клиента смогут правильно десериализовать эти типы.</span><span class="sxs-lookup"><span data-stu-id="a2162-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a2162-111">Настройка, построение и выполнение примера</span><span class="sxs-lookup"><span data-stu-id="a2162-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="a2162-112">Чтобы запустить клиент, щелкните правой кнопкой мыши решение SBGenericsVTS (6 проектов), а затем выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="a2162-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="a2162-113">В **общие свойства**выберите **запускаемым проектом**, а затем выберите **несколько запускаемых проектов**.</span><span class="sxs-lookup"><span data-stu-id="a2162-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="a2162-114">Выберите **Server** первой, затем **Client20** и затем **Client40**.</span><span class="sxs-lookup"><span data-stu-id="a2162-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="a2162-115">Выберите **запустить** действие для трех этих проектов и оставьте остальные **None**.</span><span class="sxs-lookup"><span data-stu-id="a2162-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="a2162-116">Нажмите кнопку **ОК** и нажмите клавишу F5 для запуска примера.</span><span class="sxs-lookup"><span data-stu-id="a2162-116">Click **OK** and then press F5 to run the sample.</span></span>
