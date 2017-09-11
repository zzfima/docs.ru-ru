---
title: "Certmgr.exe (средство диспетчера сертификатов)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
caps.latest.revision: 27
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bd5d1011a8f8aeadfc7729c3a4f6f56a033110a9
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="f0e35-102">Certmgr.exe (средство диспетчера сертификатов)</span><span class="sxs-lookup"><span data-stu-id="f0e35-102">Certmgr.exe (Certificate Manager Tool)</span></span>
<span data-ttu-id="f0e35-103">Диспетчер сертификатов (Certmgr.exe) предназначен для управления сертификатами, списками доверия сертификатов (CTL) и списками отзыва сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="f0e35-103">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="f0e35-104">Диспетчер сертификатов устанавливается автоматически вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f0e35-104">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="f0e35-105">Для запуска программы используйте [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f0e35-105">To start the tool, use the [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0e35-106">Диспетчер сертификатов (Certmgr.exe) является служебной программой командной строки, в то время как сертификаты (Certmgr.msc) — это оснастка консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="f0e35-106">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="f0e35-107">Поскольку файл Certmgr.msc обычно находится в системном каталоге Windows, при вводе `certmgr` в командной строке может загрузиться оснастка консоли управления (MMC) "Сертификаты", даже если открыта командная строка Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f0e35-107">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Visual Studio Command Prompt.</span></span> <span data-ttu-id="f0e35-108">Это происходит потому, что путь к оснастке предшествует пути к диспетчеру сертификатов в переменной среды PATH.</span><span class="sxs-lookup"><span data-stu-id="f0e35-108">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="f0e35-109">При возникновении этой проблемы команды Certmgr.exe можно выполнить, указав путь к исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="f0e35-109">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>  
  
 <span data-ttu-id="f0e35-110">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f0e35-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="f0e35-111">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="f0e35-111">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="f0e35-112">Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f0e35-112">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="f0e35-113">Общие сведения о сертификатах X.509 см. в разделе [Работа с сертификатами](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f0e35-113">For an overview of X.509 certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="f0e35-114">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="f0e35-114">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e35-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0e35-115">Syntax</span></span>  
  
```  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0e35-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0e35-116">Parameters</span></span>  
  
|<span data-ttu-id="f0e35-117">Аргумент</span><span class="sxs-lookup"><span data-stu-id="f0e35-117">Argument</span></span>|<span data-ttu-id="f0e35-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f0e35-118">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f0e35-119">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="f0e35-119">*sourceStorename*</span></span>|<span data-ttu-id="f0e35-120">Хранилище сертификатов, содержащее существующие сертификаты, списки доверия сертификатов (CTL) и списки отзыва сертификатов (CRL) для добавления, удаления, сохранения или отображения.</span><span class="sxs-lookup"><span data-stu-id="f0e35-120">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="f0e35-121">Это может быть файл хранилища или хранилище систем.</span><span class="sxs-lookup"><span data-stu-id="f0e35-121">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="f0e35-122">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="f0e35-122">*destinationStorename*</span></span>|<span data-ttu-id="f0e35-123">Конечное хранилище сертификатов или файл.</span><span class="sxs-lookup"><span data-stu-id="f0e35-123">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="f0e35-124">Параметр</span><span class="sxs-lookup"><span data-stu-id="f0e35-124">Option</span></span>|<span data-ttu-id="f0e35-125">Описание</span><span class="sxs-lookup"><span data-stu-id="f0e35-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f0e35-126">**/add**</span><span class="sxs-lookup"><span data-stu-id="f0e35-126">**/add**</span></span>|<span data-ttu-id="f0e35-127">Добавляет сертификаты, CTL и CRL в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f0e35-127">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="f0e35-128">**/all**</span><span class="sxs-lookup"><span data-stu-id="f0e35-128">**/all**</span></span>|<span data-ttu-id="f0e35-129">Добавляет все записи при использовании параметра **/add**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-129">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="f0e35-130">Удаляет все записи при использовании параметра **/del**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-130">Deletes all entries when used with **/del**.</span></span> <span data-ttu-id="f0e35-131">Отображает все записи при использовании без параметров **/add** или **/del**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-131">Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="f0e35-132">Параметр **/all** нельзя использовать вместе с параметром **/put**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-132">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="f0e35-133">**/c**</span><span class="sxs-lookup"><span data-stu-id="f0e35-133">**/c**</span></span>|<span data-ttu-id="f0e35-134">Добавляет сертификаты при использовании параметра **/add**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-134">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="f0e35-135">Удаляет сертификаты при использовании параметра **/del**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-135">Deletes certificates when used with **/del**.</span></span> <span data-ttu-id="f0e35-136">Сохраняет сертификаты при использовании параметра **/put**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-136">Saves certificates when used with **/put**.</span></span> <span data-ttu-id="f0e35-137">Отображает сертификаты при использовании без параметра **/add**, **/del** или **/put**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-137">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="f0e35-138">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="f0e35-138">**/CRL**</span></span>|<span data-ttu-id="f0e35-139">При использовании с параметром **/add** добавляет списки отзыва сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="f0e35-139">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="f0e35-140">При использовании с параметром **/del** удаляет списки отзыва сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="f0e35-140">Deletes CRLs when used with **/del**.</span></span> <span data-ttu-id="f0e35-141">Сохраняет списки CRL при использовании с параметром **/put**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-141">Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="f0e35-142">Отображает списки отзыва сертификатов (CRL) при использовании без параметра **/add**, **/del** или **/put**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-142">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="f0e35-143">**/CTL**</span><span class="sxs-lookup"><span data-stu-id="f0e35-143">**/CTL**</span></span>|<span data-ttu-id="f0e35-144">При использовании с параметром **/add** добавляет списки доверия сертификатов (CTL).</span><span class="sxs-lookup"><span data-stu-id="f0e35-144">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="f0e35-145">При использовании с параметром **/del** удаляет списки доверия сертификатов (CTL).</span><span class="sxs-lookup"><span data-stu-id="f0e35-145">Deletes CTLs when used with **/del**.</span></span> <span data-ttu-id="f0e35-146">Сохраняет списки CTL при использовании с параметром **/put**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-146">Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="f0e35-147">Отображает списки доверия сертификатов (CTL) при использовании без параметра **/add**, **/del** или **/put**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-147">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="f0e35-148">**/del**</span><span class="sxs-lookup"><span data-stu-id="f0e35-148">**/del**</span></span>|<span data-ttu-id="f0e35-149">Удаляет сертификаты, CTL и CRL из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f0e35-149">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="f0e35-150">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="f0e35-150">**/e** *encodingType*</span></span>|<span data-ttu-id="f0e35-151">Указывает тип шифрования сертификата.</span><span class="sxs-lookup"><span data-stu-id="f0e35-151">Specifies the certificate encoding type.</span></span> <span data-ttu-id="f0e35-152">Значение по умолчанию — `X509_ASN_ENCODING`.</span><span class="sxs-lookup"><span data-stu-id="f0e35-152">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="f0e35-153">**/f** *dwFlags*</span><span class="sxs-lookup"><span data-stu-id="f0e35-153">**/f** *dwFlags*</span></span>|<span data-ttu-id="f0e35-154">Задает открытый флаг хранилища.</span><span class="sxs-lookup"><span data-stu-id="f0e35-154">Specifies the store open flag.</span></span> <span data-ttu-id="f0e35-155">Это параметр *dwFlags*, передаваемый методу **CertOpenStore**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-155">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="f0e35-156">По умолчанию используется значение CERT_SYSTEM_STORE_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="f0e35-156">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="f0e35-157">Этот параметр обрабатывается, только если задан параметр **/y**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-157">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="f0e35-158">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="f0e35-158">**/h**[**elp**]</span></span>|<span data-ttu-id="f0e35-159">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="f0e35-159">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="f0e35-160">**/n** *nam*</span><span class="sxs-lookup"><span data-stu-id="f0e35-160">**/n** *nam*</span></span>|<span data-ttu-id="f0e35-161">Задает общее имя добавляемого, удаляемого или сохраняемого сертификата.</span><span class="sxs-lookup"><span data-stu-id="f0e35-161">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="f0e35-162">Этот параметр может применяться только для сертификатов, его нельзя задавать для CTL и CRL.</span><span class="sxs-lookup"><span data-stu-id="f0e35-162">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="f0e35-163">**/put**</span><span class="sxs-lookup"><span data-stu-id="f0e35-163">**/put**</span></span>|<span data-ttu-id="f0e35-164">Сохраняет в файл сертификат X.509, CTL или CRL из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f0e35-164">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="f0e35-165">Файл сохраняется в формате X.509.</span><span class="sxs-lookup"><span data-stu-id="f0e35-165">The file is saved in X.509 format.</span></span> <span data-ttu-id="f0e35-166">Чтобы сохранить файл в формате PKCS #7, можно использовать параметр **/7** с параметром **/put**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-166">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="f0e35-167">За параметром **/put** должен следовать параметр **/c**, **/CTL** или **/CRL**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-167">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="f0e35-168">Параметр **/all** нельзя использовать вместе с параметром **/put**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-168">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="f0e35-169">**/r** *location*</span><span class="sxs-lookup"><span data-stu-id="f0e35-169">**/r** *location*</span></span>|<span data-ttu-id="f0e35-170">Указывает расположение системного хранилища в реестре.</span><span class="sxs-lookup"><span data-stu-id="f0e35-170">Identifies the registry location of the system store.</span></span> <span data-ttu-id="f0e35-171">Этот параметр обрабатывается, только если задан параметр **/s**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-171">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="f0e35-172">Параметр *location* должен иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="f0e35-172">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="f0e35-173">-   `currentUser` означает, что хранилище сертификатов находится в разделе HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="f0e35-173">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="f0e35-174">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f0e35-174">This is the default.</span></span><br /><span data-ttu-id="f0e35-175">-   `localMachine` означает, что хранилище сертификатов находится в разделе HKEY_LOCAL_MACHINE.</span><span class="sxs-lookup"><span data-stu-id="f0e35-175">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="f0e35-176">**/s**</span><span class="sxs-lookup"><span data-stu-id="f0e35-176">**/s**</span></span>|<span data-ttu-id="f0e35-177">Означает, что хранилище сертификатов является системным.</span><span class="sxs-lookup"><span data-stu-id="f0e35-177">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="f0e35-178">Если этот параметр не задан, хранилищем считается **StoreFile**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-178">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="f0e35-179">**/sha1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="f0e35-179">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="f0e35-180">Задает хэш SHA1 добавляемого, удаляемого или сохраняемого сертификата, CTL или CRL.</span><span class="sxs-lookup"><span data-stu-id="f0e35-180">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="f0e35-181">**/v**</span><span class="sxs-lookup"><span data-stu-id="f0e35-181">**/v**</span></span>|<span data-ttu-id="f0e35-182">Включает отображение подробных сведений о сертификатах, CTL и CRL.</span><span class="sxs-lookup"><span data-stu-id="f0e35-182">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="f0e35-183">Этот параметр невозможно использовать с параметрами **/add**, **/del** или **/put**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-183">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="f0e35-184">**/y** *provider*</span><span class="sxs-lookup"><span data-stu-id="f0e35-184">**/y** *provider*</span></span>|<span data-ttu-id="f0e35-185">Задает имя поставщика хранилища.</span><span class="sxs-lookup"><span data-stu-id="f0e35-185">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="f0e35-186">**/7**</span><span class="sxs-lookup"><span data-stu-id="f0e35-186">**/7**</span></span>|<span data-ttu-id="f0e35-187">Сохраняет конечное хранилище как объект PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="f0e35-187">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="f0e35-188">**/?**</span><span class="sxs-lookup"><span data-stu-id="f0e35-188">**/?**</span></span>|<span data-ttu-id="f0e35-189">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="f0e35-189">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0e35-190">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0e35-190">Remarks</span></span>  
 <span data-ttu-id="f0e35-191">Основные функции программы Certmgr.exe.</span><span class="sxs-lookup"><span data-stu-id="f0e35-191">Certmgr.exe performs the following basic functions:</span></span>  
  
-   <span data-ttu-id="f0e35-192">Отображение сведений о сертификатах, CTL и CRL на консоли.</span><span class="sxs-lookup"><span data-stu-id="f0e35-192">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
-   <span data-ttu-id="f0e35-193">Добавляет сертификаты, CTL и CRL в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f0e35-193">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
-   <span data-ttu-id="f0e35-194">Удаляет сертификаты, CTL и CRL из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f0e35-194">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
-   <span data-ttu-id="f0e35-195">Сохраняет в файл сертификат X.509, CTL или CRL из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f0e35-195">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="f0e35-196">Программа Certmgr.exe работает с двумя типами хранилищ сертификатов: системным и **StoreFile**.</span><span class="sxs-lookup"><span data-stu-id="f0e35-196">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="f0e35-197">Указывать тип хранилища необязательно, поскольку программа Cedrtmgr.exe может автоматически определить тип хранилища и выполнить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="f0e35-197">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="f0e35-198">При запуске программы Certmgr.exe без параметров выполняется оснастка "certmgr.msc" с графическим интерфейсом пользователя, облегчающим управление сертификатами, что также можно сделать из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f0e35-198">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="f0e35-199">В графическом интерфейсе пользователя имеется мастер импорта, копирующий сертификаты, CTL и CRL с диска в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f0e35-199">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="f0e35-200">Чтобы найти имена хранилищ X509Certificate для параметров `sourceStorename` и `destinationStorename`, можно скомпилировать и выполнить следующий код.</span><span class="sxs-lookup"><span data-stu-id="f0e35-200">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 <span data-ttu-id="f0e35-201">[!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)] [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="f0e35-201">[!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)] [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]</span></span>  
  
 <span data-ttu-id="f0e35-202">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f0e35-202">For more information about certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f0e35-203">Примеры</span><span class="sxs-lookup"><span data-stu-id="f0e35-203">Examples</span></span>  
 <span data-ttu-id="f0e35-204">Следующая команда выводит подробные сведения о содержимом системного хранилища `my`, используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f0e35-204">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```  
certmgr /v /s my  
```  
  
 <span data-ttu-id="f0e35-205">Следующая команда добавляет все сертификаты из файла `myFile.ext` в новый файл `newFile.ext`.</span><span class="sxs-lookup"><span data-stu-id="f0e35-205">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="f0e35-206">Следующая команда добавляет сертификат в файле `testcert.cer` в хранилище системы `my`.</span><span class="sxs-lookup"><span data-stu-id="f0e35-206">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="f0e35-207">Следующая команда добавляет сертификат в файле `TrustedCert.cer` в хранилище корневых сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f0e35-207">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="f0e35-208">Следующая команда сохраняет сертификат с общим именем `myCert` в системном хранилище `my` в файл `newCert.cer`.</span><span class="sxs-lookup"><span data-stu-id="f0e35-208">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="f0e35-209">Следующая команда удаляет все CTL из системного хранилища `my` и сохраняет полученное хранилище в файл `newStore.str`.</span><span class="sxs-lookup"><span data-stu-id="f0e35-209">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="f0e35-210">Следующая команда сохраняет сертификат в системном хранилище `my` в файл `newFile`.</span><span class="sxs-lookup"><span data-stu-id="f0e35-210">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="f0e35-211">Программа запросит у пользователя номер сертификата из хранилища `my`, который следует поместить в файл `newFile`.</span><span class="sxs-lookup"><span data-stu-id="f0e35-211">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0e35-212">См. также</span><span class="sxs-lookup"><span data-stu-id="f0e35-212">See Also</span></span>  
 <span data-ttu-id="f0e35-213">[Инструменты](../../../docs/framework/tools/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0e35-213">[Tools](../../../docs/framework/tools/index.md) </span></span>  
 <span data-ttu-id="f0e35-214">[Makecert.exe (средство создания сертификатов)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) </span><span class="sxs-lookup"><span data-stu-id="f0e35-214">[Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) </span></span>  
 [<span data-ttu-id="f0e35-215">Командные строки</span><span class="sxs-lookup"><span data-stu-id="f0e35-215">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

