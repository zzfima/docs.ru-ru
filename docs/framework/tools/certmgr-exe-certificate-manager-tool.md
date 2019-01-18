---
title: Certmgr.exe (средство диспетчера сертификатов)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e0274b1f1f0bc0ec6de7490c4602e5813e4d46f
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221613"
---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="45ae7-102">Certmgr.exe (средство диспетчера сертификатов)</span><span class="sxs-lookup"><span data-stu-id="45ae7-102">Certmgr.exe (Certificate Manager Tool)</span></span>
<span data-ttu-id="45ae7-103">Диспетчер сертификатов (Certmgr.exe) предназначен для управления сертификатами, списками доверия сертификатов (CTL) и списками отзыва сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="45ae7-103">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="45ae7-104">Диспетчер сертификатов устанавливается автоматически вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="45ae7-104">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="45ae7-105">Для запуска программы используйте [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="45ae7-105">To start the tool, use the [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45ae7-106">Диспетчер сертификатов (Certmgr.exe) является служебной программой командной строки, в то время как сертификаты (Certmgr.msc) — это оснастка консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="45ae7-106">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="45ae7-107">Поскольку файл Certmgr.msc обычно находится в системном каталоге Windows, при вводе `certmgr` в командной строке может загрузиться оснастка консоли управления (MMC) "Сертификаты", даже если открыта командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="45ae7-107">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="45ae7-108">Это происходит потому, что путь к оснастке предшествует пути к диспетчеру сертификатов в переменной среды PATH.</span><span class="sxs-lookup"><span data-stu-id="45ae7-108">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="45ae7-109">При возникновении этой проблемы команды Certmgr.exe можно выполнить, указав путь к исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="45ae7-109">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>  
  
 <span data-ttu-id="45ae7-110">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="45ae7-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="45ae7-111">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика для Visual Studio (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="45ae7-111">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="45ae7-112">Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="45ae7-112">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="45ae7-113">Общие сведения о сертификатах X.509 см. в разделе [Работа с сертификатами](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="45ae7-113">For an overview of X.509 certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="45ae7-114">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="45ae7-114">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45ae7-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45ae7-115">Syntax</span></span>  
  
```  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45ae7-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="45ae7-116">Parameters</span></span>  
  
|<span data-ttu-id="45ae7-117">Аргумент</span><span class="sxs-lookup"><span data-stu-id="45ae7-117">Argument</span></span>|<span data-ttu-id="45ae7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="45ae7-118">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="45ae7-119">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="45ae7-119">*sourceStorename*</span></span>|<span data-ttu-id="45ae7-120">Хранилище сертификатов, содержащее существующие сертификаты, списки доверия сертификатов (CTL) и списки отзыва сертификатов (CRL) для добавления, удаления, сохранения или отображения.</span><span class="sxs-lookup"><span data-stu-id="45ae7-120">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="45ae7-121">Это может быть файл хранилища или хранилище систем.</span><span class="sxs-lookup"><span data-stu-id="45ae7-121">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="45ae7-122">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="45ae7-122">*destinationStorename*</span></span>|<span data-ttu-id="45ae7-123">Конечное хранилище сертификатов или файл.</span><span class="sxs-lookup"><span data-stu-id="45ae7-123">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="45ae7-124">Параметр</span><span class="sxs-lookup"><span data-stu-id="45ae7-124">Option</span></span>|<span data-ttu-id="45ae7-125">Описание</span><span class="sxs-lookup"><span data-stu-id="45ae7-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="45ae7-126">**/add**</span><span class="sxs-lookup"><span data-stu-id="45ae7-126">**/add**</span></span>|<span data-ttu-id="45ae7-127">Добавляет сертификаты, CTL и CRL в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="45ae7-127">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="45ae7-128">**/all**</span><span class="sxs-lookup"><span data-stu-id="45ae7-128">**/all**</span></span>|<span data-ttu-id="45ae7-129">Добавляет все записи при использовании параметра **/add**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-129">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="45ae7-130">Удаляет все записи при использовании параметра **/del**. Отображает все записи при использовании без параметров **/add** или **/del**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-130">Deletes all entries when used with **/del**. Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="45ae7-131">Параметр **/all** нельзя использовать вместе с параметром **/put**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-131">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="45ae7-132">**/c**</span><span class="sxs-lookup"><span data-stu-id="45ae7-132">**/c**</span></span>|<span data-ttu-id="45ae7-133">Добавляет сертификаты при использовании параметра **/add**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-133">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="45ae7-134">Удаляет сертификаты при использовании параметра **/del**. Сохраняет сертификаты при использовании параметра **/put**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-134">Deletes certificates when used with **/del**. Saves certificates when used with **/put**.</span></span> <span data-ttu-id="45ae7-135">Отображает сертификаты при использовании без параметра **/add**, **/del** или **/put**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-135">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="45ae7-136">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="45ae7-136">**/CRL**</span></span>|<span data-ttu-id="45ae7-137">При использовании с параметром **/add** добавляет списки отзыва сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="45ae7-137">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="45ae7-138">При использовании с параметром **/del** удаляет списки отзыва сертификатов (CRL). Сохраняет списки CRL при использовании с параметром **/put**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-138">Deletes CRLs when used with **/del**. Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="45ae7-139">Отображает списки отзыва сертификатов (CRL) при использовании без параметра **/add**, **/del** или **/put**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-139">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="45ae7-140">**/CTL**</span><span class="sxs-lookup"><span data-stu-id="45ae7-140">**/CTL**</span></span>|<span data-ttu-id="45ae7-141">При использовании с параметром **/add** добавляет списки доверия сертификатов (CTL).</span><span class="sxs-lookup"><span data-stu-id="45ae7-141">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="45ae7-142">При использовании с параметром **/del** удаляет списки доверия сертификатов (CTL). Сохраняет списки CTL при использовании с параметром **/put**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-142">Deletes CTLs when used with **/del**. Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="45ae7-143">Отображает списки доверия сертификатов (CTL) при использовании без параметра **/add**, **/del** или **/put**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-143">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="45ae7-144">**/del**</span><span class="sxs-lookup"><span data-stu-id="45ae7-144">**/del**</span></span>|<span data-ttu-id="45ae7-145">Удаляет сертификаты, CTL и CRL из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="45ae7-145">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="45ae7-146">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="45ae7-146">**/e** *encodingType*</span></span>|<span data-ttu-id="45ae7-147">Указывает тип шифрования сертификата.</span><span class="sxs-lookup"><span data-stu-id="45ae7-147">Specifies the certificate encoding type.</span></span> <span data-ttu-id="45ae7-148">Значение по умолчанию — `X509_ASN_ENCODING`.</span><span class="sxs-lookup"><span data-stu-id="45ae7-148">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="45ae7-149">**/f** *dwFlags*</span><span class="sxs-lookup"><span data-stu-id="45ae7-149">**/f** *dwFlags*</span></span>|<span data-ttu-id="45ae7-150">Задает открытый флаг хранилища.</span><span class="sxs-lookup"><span data-stu-id="45ae7-150">Specifies the store open flag.</span></span> <span data-ttu-id="45ae7-151">Это параметр *dwFlags*, передаваемый методу **CertOpenStore**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-151">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="45ae7-152">По умолчанию используется значение CERT_SYSTEM_STORE_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="45ae7-152">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="45ae7-153">Этот параметр обрабатывается, только если задан параметр **/y**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-153">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="45ae7-154">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="45ae7-154">**/h**[**elp**]</span></span>|<span data-ttu-id="45ae7-155">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="45ae7-155">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="45ae7-156">**/n** *nam*</span><span class="sxs-lookup"><span data-stu-id="45ae7-156">**/n** *nam*</span></span>|<span data-ttu-id="45ae7-157">Задает общее имя добавляемого, удаляемого или сохраняемого сертификата.</span><span class="sxs-lookup"><span data-stu-id="45ae7-157">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="45ae7-158">Этот параметр может применяться только для сертификатов, его нельзя задавать для CTL и CRL.</span><span class="sxs-lookup"><span data-stu-id="45ae7-158">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="45ae7-159">**/put**</span><span class="sxs-lookup"><span data-stu-id="45ae7-159">**/put**</span></span>|<span data-ttu-id="45ae7-160">Сохраняет в файл сертификат X.509, CTL или CRL из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="45ae7-160">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="45ae7-161">Файл сохраняется в формате X.509.</span><span class="sxs-lookup"><span data-stu-id="45ae7-161">The file is saved in X.509 format.</span></span> <span data-ttu-id="45ae7-162">Чтобы сохранить файл в формате PKCS #7, можно использовать параметр **/7** с параметром **/put**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-162">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="45ae7-163">За параметром **/put** должен следовать параметр **/c**, **/CTL** или **/CRL**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-163">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="45ae7-164">Параметр **/all** нельзя использовать вместе с параметром **/put**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-164">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="45ae7-165">**/r** *location*</span><span class="sxs-lookup"><span data-stu-id="45ae7-165">**/r** *location*</span></span>|<span data-ttu-id="45ae7-166">Указывает расположение системного хранилища в реестре.</span><span class="sxs-lookup"><span data-stu-id="45ae7-166">Identifies the registry location of the system store.</span></span> <span data-ttu-id="45ae7-167">Этот параметр обрабатывается, только если задан параметр **/s**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-167">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="45ae7-168">Параметр *location* должен иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="45ae7-168">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="45ae7-169">-   `currentUser` означает, что хранилище сертификатов находится в разделе HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="45ae7-169">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="45ae7-170">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45ae7-170">This is the default.</span></span><br /><span data-ttu-id="45ae7-171">-   `localMachine` означает, что хранилище сертификатов находится в разделе HKEY_LOCAL_MACHINE.</span><span class="sxs-lookup"><span data-stu-id="45ae7-171">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="45ae7-172">**/s**</span><span class="sxs-lookup"><span data-stu-id="45ae7-172">**/s**</span></span>|<span data-ttu-id="45ae7-173">Означает, что хранилище сертификатов является системным.</span><span class="sxs-lookup"><span data-stu-id="45ae7-173">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="45ae7-174">Если этот параметр не задан, хранилищем считается **StoreFile**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-174">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="45ae7-175">**/sha1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="45ae7-175">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="45ae7-176">Задает хэш SHA1 добавляемого, удаляемого или сохраняемого сертификата, CTL или CRL.</span><span class="sxs-lookup"><span data-stu-id="45ae7-176">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="45ae7-177">**/v**</span><span class="sxs-lookup"><span data-stu-id="45ae7-177">**/v**</span></span>|<span data-ttu-id="45ae7-178">Включает отображение подробных сведений о сертификатах, CTL и CRL.</span><span class="sxs-lookup"><span data-stu-id="45ae7-178">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="45ae7-179">Этот параметр невозможно использовать с параметрами **/add**, **/del** или **/put**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-179">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="45ae7-180">**/y** *provider*</span><span class="sxs-lookup"><span data-stu-id="45ae7-180">**/y** *provider*</span></span>|<span data-ttu-id="45ae7-181">Задает имя поставщика хранилища.</span><span class="sxs-lookup"><span data-stu-id="45ae7-181">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="45ae7-182">**/7**</span><span class="sxs-lookup"><span data-stu-id="45ae7-182">**/7**</span></span>|<span data-ttu-id="45ae7-183">Сохраняет конечное хранилище как объект PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="45ae7-183">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="45ae7-184">**/?**</span><span class="sxs-lookup"><span data-stu-id="45ae7-184">**/?**</span></span>|<span data-ttu-id="45ae7-185">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="45ae7-185">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45ae7-186">Примечания</span><span class="sxs-lookup"><span data-stu-id="45ae7-186">Remarks</span></span>  
 <span data-ttu-id="45ae7-187">Основные функции программы Certmgr.exe.</span><span class="sxs-lookup"><span data-stu-id="45ae7-187">Certmgr.exe performs the following basic functions:</span></span>  
  
-   <span data-ttu-id="45ae7-188">Отображение сведений о сертификатах, CTL и CRL на консоли.</span><span class="sxs-lookup"><span data-stu-id="45ae7-188">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
-   <span data-ttu-id="45ae7-189">Добавляет сертификаты, CTL и CRL в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="45ae7-189">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
-   <span data-ttu-id="45ae7-190">Удаляет сертификаты, CTL и CRL из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="45ae7-190">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
-   <span data-ttu-id="45ae7-191">Сохраняет в файл сертификат X.509, CTL или CRL из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="45ae7-191">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="45ae7-192">Программа Certmgr.exe работает с двумя типами хранилищ сертификатов: системным и **StoreFile**.</span><span class="sxs-lookup"><span data-stu-id="45ae7-192">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="45ae7-193">Указывать тип хранилища необязательно, поскольку программа Cedrtmgr.exe может автоматически определить тип хранилища и выполнить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="45ae7-193">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="45ae7-194">При запуске программы Certmgr.exe без параметров выполняется оснастка "certmgr.msc" с графическим интерфейсом пользователя, облегчающим управление сертификатами, что также можно сделать из командной строки.</span><span class="sxs-lookup"><span data-stu-id="45ae7-194">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="45ae7-195">В графическом интерфейсе пользователя имеется мастер импорта, копирующий сертификаты, CTL и CRL с диска в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="45ae7-195">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="45ae7-196">Чтобы найти имена хранилищ X509Certificate для параметров `sourceStorename` и `destinationStorename`, можно скомпилировать и выполнить следующий код.</span><span class="sxs-lookup"><span data-stu-id="45ae7-196">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 <span data-ttu-id="45ae7-197">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="45ae7-197">For more information about certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="45ae7-198">Примеры</span><span class="sxs-lookup"><span data-stu-id="45ae7-198">Examples</span></span>  
 <span data-ttu-id="45ae7-199">Следующая команда выводит подробные сведения о содержимом системного хранилища `my`, используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45ae7-199">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```  
certmgr /v /s my  
```  
  
 <span data-ttu-id="45ae7-200">Следующая команда добавляет все сертификаты из файла `myFile.ext` в новый файл `newFile.ext`.</span><span class="sxs-lookup"><span data-stu-id="45ae7-200">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="45ae7-201">Следующая команда добавляет сертификат в файле `testcert.cer` в хранилище системы `my`.</span><span class="sxs-lookup"><span data-stu-id="45ae7-201">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="45ae7-202">Следующая команда добавляет сертификат в файле `TrustedCert.cer` в хранилище корневых сертификатов.</span><span class="sxs-lookup"><span data-stu-id="45ae7-202">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="45ae7-203">Следующая команда сохраняет сертификат с общим именем `myCert` в системном хранилище `my` в файл `newCert.cer`.</span><span class="sxs-lookup"><span data-stu-id="45ae7-203">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="45ae7-204">Следующая команда удаляет все CTL из системного хранилища `my` и сохраняет полученное хранилище в файл `newStore.str`.</span><span class="sxs-lookup"><span data-stu-id="45ae7-204">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="45ae7-205">Следующая команда сохраняет сертификат в системном хранилище `my` в файл `newFile`.</span><span class="sxs-lookup"><span data-stu-id="45ae7-205">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="45ae7-206">Программа запросит у пользователя номер сертификата из хранилища `my`, который следует поместить в файл `newFile`.</span><span class="sxs-lookup"><span data-stu-id="45ae7-206">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="45ae7-207">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="45ae7-207">See Also</span></span>  
 [<span data-ttu-id="45ae7-208">Инструменты</span><span class="sxs-lookup"><span data-stu-id="45ae7-208">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="45ae7-209">Makecert.exe (средство создания сертификатов)</span><span class="sxs-lookup"><span data-stu-id="45ae7-209">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)  
 [<span data-ttu-id="45ae7-210">Командные строки</span><span class="sxs-lookup"><span data-stu-id="45ae7-210">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
