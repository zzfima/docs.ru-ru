---
title: Интерпретация сетевой трассировки
ms.date: 03/30/2017
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
ms.openlocfilehash: 00df193671255e7b40f5c4b86ee952a3e20e3a40
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177571"
---
# <a name="interpreting-network-tracing"></a><span data-ttu-id="aee32-102">Интерпретация сетевой трассировки</span><span class="sxs-lookup"><span data-stu-id="aee32-102">Interpreting Network Tracing</span></span>
<span data-ttu-id="aee32-103">Если включена трассировка сети, ее можно использовать для записи вызовов, осуществляемых приложением к различным членам класса <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="aee32-103">When network tracing is enabled, you can use tracing to capture calls your application makes to various <xref:System.Net> class members.</span></span> <span data-ttu-id="aee32-104">Выходные данные этих вызовов могут быть аналогичны приведенным далее.</span><span class="sxs-lookup"><span data-stu-id="aee32-104">The output from these calls may be similar to the following examples.</span></span>  
  
```  
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61  
```  
  
 <span data-ttu-id="aee32-105">В приведенном выше примере [588] — уникальный идентификатор текущего потока.</span><span class="sxs-lookup"><span data-stu-id="aee32-105">In the preceding example, [588] is the current thread's unique identifier.</span></span> <span data-ttu-id="aee32-106">(4357) и (4387) — метки времени, обозначающие количество миллисекунд, прошедших с момента запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="aee32-106">(4357) and (4387) are timestamps denoting the number of milliseconds that have elapsed since the application started.</span></span> <span data-ttu-id="aee32-107">Данные, которые идут за меткой времени, указывают на приложение, начинающее и завершающее метод **Socket.Send**.</span><span class="sxs-lookup"><span data-stu-id="aee32-107">The data following the timestamp shows the application entering and exiting the method **Socket.Send**.</span></span> <span data-ttu-id="aee32-108">Объект, выполняющий метод **Send**, имеет уникальный идентификатор 33574638.</span><span class="sxs-lookup"><span data-stu-id="aee32-108">The object executing the **Send** method has 33574638 as its unique identifier.</span></span> <span data-ttu-id="aee32-109">Трассировка завершения метода содержит возвращаемое значение (61 в предыдущем примере).</span><span class="sxs-lookup"><span data-stu-id="aee32-109">The method exit trace includes the return value (61 in the preceding example).</span></span>  
  
 <span data-ttu-id="aee32-110">Сетевая трассировка может записывать сетевой трафик, отправленный из приложения или полученный им с помощью протоколов уровня приложения, таких как HTTP.</span><span class="sxs-lookup"><span data-stu-id="aee32-110">Network traces can capture network traffic that is sent from or received by your application using application-level protocols such as Hypertext Transfer Protocol (HTTP).</span></span> <span data-ttu-id="aee32-111">Эти данные могут захватываться как текст и шестнадцатеричные данные.</span><span class="sxs-lookup"><span data-stu-id="aee32-111">This data can be captured as text and, optionally, hexadecimal data.</span></span> <span data-ttu-id="aee32-112">Шестнадцатеричные данные доступны при указании **includehex** в качестве значения атрибута **tracemode**.</span><span class="sxs-lookup"><span data-stu-id="aee32-112">Hexadecimal data is available when you specify **includehex** as the value of the **tracemode** attribute.</span></span> <span data-ttu-id="aee32-113">(Подробные сведения об этом атрибуте см. в разделе [Практическое руководство. Настройка трассировки сети](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).) Следующий пример трассировки был создан с помощью **includehex**.</span><span class="sxs-lookup"><span data-stu-id="aee32-113">(For detailed information about this attribute, see [How to: Configure Network Tracing](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).) The following example trace was generated using **includehex**.</span></span>  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 <span data-ttu-id="aee32-114">Чтобы опустить шестнадцатеричные данные, укажите **protocolonly** в качестве значения атрибута **tracemode**.</span><span class="sxs-lookup"><span data-stu-id="aee32-114">To omit hexadecimal data, specify **protocolonly** as the value for the **tracemode** attribute.</span></span> <span data-ttu-id="aee32-115">В следующем примере показана трассировка с указанным значением **protocolonly**.</span><span class="sxs-lookup"><span data-stu-id="aee32-115">The following example shows the trace when **protocolonly** is specified.</span></span>  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a><span data-ttu-id="aee32-116">См. также</span><span class="sxs-lookup"><span data-stu-id="aee32-116">See also</span></span>

- [<span data-ttu-id="aee32-117">Включение сетевой трассировки</span><span class="sxs-lookup"><span data-stu-id="aee32-117">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)
- [<span data-ttu-id="aee32-118">Практическое руководство. Настройка трассировки сети</span><span class="sxs-lookup"><span data-stu-id="aee32-118">How to: Configure Network Tracing</span></span>](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)
- [<span data-ttu-id="aee32-119">Трассировка сети в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="aee32-119">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)
