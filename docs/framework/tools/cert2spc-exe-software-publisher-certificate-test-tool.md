---
title: Cert2spc.exe (средство проверки сертификата издателя программного обеспечения)
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75c782cbe7a45c05212c99448df6e8536a17f38d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50202739"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="df07a-102">Cert2spc.exe (средство проверки сертификата издателя программного обеспечения)</span><span class="sxs-lookup"><span data-stu-id="df07a-102">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>
<span data-ttu-id="df07a-103">Программа для проверки сертификата издателя программного обеспечения служит для создания сертификата издателя программного обеспечения (SPC) из одного или нескольких сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="df07a-103">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="df07a-104">Программа Cert2spc.exe используется только для тестирования.</span><span class="sxs-lookup"><span data-stu-id="df07a-104">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="df07a-105">Действительный сертификат SPC можно получить в центрах сертификации, таких как VeriSign и Thawte.</span><span class="sxs-lookup"><span data-stu-id="df07a-105">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="df07a-106">Дополнительные сведения о создании сертификатов X.509 см. в разделе [Makecert.exe (средство создания сертификатов)](/windows/desktop/SecCrypto/makecert).</span><span class="sxs-lookup"><span data-stu-id="df07a-106">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert).</span></span>  
  
 <span data-ttu-id="df07a-107">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="df07a-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="df07a-108">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="df07a-108">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="df07a-109">Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="df07a-109">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="df07a-110">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="df07a-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df07a-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df07a-111">Syntax</span></span>  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df07a-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="df07a-112">Parameters</span></span>  
  
|<span data-ttu-id="df07a-113">Аргумент</span><span class="sxs-lookup"><span data-stu-id="df07a-113">Argument</span></span>|<span data-ttu-id="df07a-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="df07a-114">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="df07a-115">Имя сертификата X.509, включаемого в SPC-файл.</span><span class="sxs-lookup"><span data-stu-id="df07a-115">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="df07a-116">Можно указать несколько имен, разделенных пробелами.</span><span class="sxs-lookup"><span data-stu-id="df07a-116">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="df07a-117">Имя списка отзыва сертификатов для включения в SPC-файл.</span><span class="sxs-lookup"><span data-stu-id="df07a-117">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="df07a-118">Можно указать несколько имен, разделенных пробелами.</span><span class="sxs-lookup"><span data-stu-id="df07a-118">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="df07a-119">Имя объекта PKCS #7, который будет содержать сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="df07a-119">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="df07a-120">Параметр</span><span class="sxs-lookup"><span data-stu-id="df07a-120">Option</span></span>|<span data-ttu-id="df07a-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="df07a-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="df07a-122">**/?**</span><span class="sxs-lookup"><span data-stu-id="df07a-122">**/?**</span></span>|<span data-ttu-id="df07a-123">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="df07a-123">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="df07a-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="df07a-124">Examples</span></span>  
 <span data-ttu-id="df07a-125">Следующая команда создает SPC-файл из файла `myCertificate.cer` и помещает его в файл `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="df07a-125">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="df07a-126">Следующая команда создает SPC-файл из файлов `oneCertificate.cer` и `twoCertificate.cer` и помещает его в файл `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="df07a-126">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="df07a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="df07a-127">See Also</span></span>  
 [<span data-ttu-id="df07a-128">Инструменты</span><span class="sxs-lookup"><span data-stu-id="df07a-128">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="df07a-129">Makecert.exe (средство создания сертификатов)</span><span class="sxs-lookup"><span data-stu-id="df07a-129">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)  
 [<span data-ttu-id="df07a-130">Командные строки</span><span class="sxs-lookup"><span data-stu-id="df07a-130">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
