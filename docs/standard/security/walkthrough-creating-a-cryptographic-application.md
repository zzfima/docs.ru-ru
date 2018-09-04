---
title: Пошаговое руководство. Создание криптографического приложения
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET Framework], example
- cryptography [NET Framework], cryptographic application example
- cryptography [NET Framework], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a01da268a8347e93982604520f9dcb1d4e91327d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501619"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="393d0-102">Пошаговое руководство. Создание криптографического приложения</span><span class="sxs-lookup"><span data-stu-id="393d0-102">Walkthrough: Creating a Cryptographic Application</span></span>
<span data-ttu-id="393d0-103">В этом пошаговом руководстве показано, как зашифровать и расшифровать содержимое.</span><span class="sxs-lookup"><span data-stu-id="393d0-103">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="393d0-104">Пример кода предназначен для приложения Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="393d0-104">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="393d0-105">Это приложение не демонстрирует реальные сценарии, такие как использование смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="393d0-105">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="393d0-106">Вместо этого оно демонстрирует основные принципы шифрования и расшифровки.</span><span class="sxs-lookup"><span data-stu-id="393d0-106">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
 <span data-ttu-id="393d0-107">В этом пошаговом руководстве использует следующие правила шифрования:</span><span class="sxs-lookup"><span data-stu-id="393d0-107">This walkthrough uses the following guidelines for encryption:</span></span>  
  
-   <span data-ttu-id="393d0-108">Используйте класс <xref:System.Security.Cryptography.RijndaelManaged> с симметричным алгоритмом для шифрования и расшифровки данных при помощи автоматически созданных <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> и <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span><span class="sxs-lookup"><span data-stu-id="393d0-108">Use the <xref:System.Security.Cryptography.RijndaelManaged> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
-   <span data-ttu-id="393d0-109">Используйте <xref:System.Security.Cryptography.RSACryptoServiceProvider> с асимметричным алгоритмом для шифрования и расшифровки ключа для данных, зашифрованных при помощи <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="393d0-109">Use the <xref:System.Security.Cryptography.RSACryptoServiceProvider>, an asymmetric algorithm, to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.RijndaelManaged>.</span></span> <span data-ttu-id="393d0-110">Асимметричные алгоритмы лучше подходят для небольших объемов данных, таких как ключ.</span><span class="sxs-lookup"><span data-stu-id="393d0-110">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="393d0-111">Если вы хотите защитить данные на компьютере, а не обмениваться зашифрованным содержимым с другими людьми, рекомендуется использовать классы <xref:System.Security.Cryptography.ProtectedData> или <xref:System.Security.Cryptography.ProtectedMemory>.</span><span class="sxs-lookup"><span data-stu-id="393d0-111">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> or <xref:System.Security.Cryptography.ProtectedMemory> classes.</span></span>  
  
 <span data-ttu-id="393d0-112">В следующей таблице указаны задачи шифрования из этого раздела.</span><span class="sxs-lookup"><span data-stu-id="393d0-112">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="393d0-113">Задача</span><span class="sxs-lookup"><span data-stu-id="393d0-113">Task</span></span>|<span data-ttu-id="393d0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="393d0-114">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="393d0-115">Создание приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="393d0-115">Creating a Windows Forms application</span></span>|<span data-ttu-id="393d0-116">Выводит список элементов управления, необходимых для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="393d0-116">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="393d0-117">Объявление глобальных объектов</span><span class="sxs-lookup"><span data-stu-id="393d0-117">Declaring global objects</span></span>|<span data-ttu-id="393d0-118">Объявляет, что строковые переменные пути <xref:System.Security.Cryptography.CspParameters> и <xref:System.Security.Cryptography.RSACryptoServiceProvider> имеют глобальный контекст класса <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="393d0-118">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="393d0-119">Создание асимметричного ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-119">Creating an asymmetric key</span></span>|<span data-ttu-id="393d0-120">Создает пару значений открытого и закрытого асимметричного ключа и присваивает ей имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="393d0-120">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="393d0-121">Шифрование файла</span><span class="sxs-lookup"><span data-stu-id="393d0-121">Encrypting a file</span></span>|<span data-ttu-id="393d0-122">Отображает диалоговое окно, где можно выбрать шифруемый файл, и шифрует этот файл.</span><span class="sxs-lookup"><span data-stu-id="393d0-122">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="393d0-123">Расшифровка файла</span><span class="sxs-lookup"><span data-stu-id="393d0-123">Decrypting a file</span></span>|<span data-ttu-id="393d0-124">Отображает диалоговое окно, где можно выбрать зашифрованный файл, и выполняет расшифровку этого файла.</span><span class="sxs-lookup"><span data-stu-id="393d0-124">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="393d0-125">Получение закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-125">Getting a private key</span></span>|<span data-ttu-id="393d0-126">Возвращает полную пару ключей при помощи имени контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="393d0-126">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="393d0-127">Экспорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-127">Exporting a public key</span></span>|<span data-ttu-id="393d0-128">Сохраняет ключ в XML-файл только с открытыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="393d0-128">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="393d0-129">Импорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-129">Importing a public key</span></span>|<span data-ttu-id="393d0-130">Загружает ключ из XML-файла в контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="393d0-130">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="393d0-131">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="393d0-131">Testing the application</span></span>|<span data-ttu-id="393d0-132">Список процедур для тестирования этого приложения.</span><span class="sxs-lookup"><span data-stu-id="393d0-132">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="393d0-133">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="393d0-133">Prerequisites</span></span>  
 <span data-ttu-id="393d0-134">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="393d0-134">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="393d0-135">Ссылки на пространства имен <xref:System.IO> и <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="393d0-135">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="393d0-136">Создание приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="393d0-136">Creating a Windows Forms Application</span></span>  
 <span data-ttu-id="393d0-137">Большинство примеров кода в этом пошаговом руководстве предназначено для использования в качестве обработчиков событий для элементов управления кнопок.</span><span class="sxs-lookup"><span data-stu-id="393d0-137">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="393d0-138">В следующей таблице перечислены элементы управления, необходимые для образца приложения, и их имена в соответствии с примерами кода.</span><span class="sxs-lookup"><span data-stu-id="393d0-138">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="393d0-139">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="393d0-139">Control</span></span>|<span data-ttu-id="393d0-140">name</span><span class="sxs-lookup"><span data-stu-id="393d0-140">Name</span></span>|<span data-ttu-id="393d0-141">Текстовое свойство (при необходимости)</span><span class="sxs-lookup"><span data-stu-id="393d0-141">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="393d0-142">Шифрование файла</span><span class="sxs-lookup"><span data-stu-id="393d0-142">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="393d0-143">Расшифровка файла</span><span class="sxs-lookup"><span data-stu-id="393d0-143">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="393d0-144">Создание ключей</span><span class="sxs-lookup"><span data-stu-id="393d0-144">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="393d0-145">Экспорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-145">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="393d0-146">Импорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-146">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="393d0-147">Получение закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-147">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="393d0-148">Дважды щелкните кнопки в конструкторе Visual Studio, чтобы создать для них обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="393d0-148">Double-click the buttons in the  Visual Studio designer to create their event handlers.</span></span>  
  
## <a name="declaring-global-objects"></a><span data-ttu-id="393d0-149">Объявление глобальных объектов</span><span class="sxs-lookup"><span data-stu-id="393d0-149">Declaring Global Objects</span></span>  
 <span data-ttu-id="393d0-150">Добавьте в конструктор формы следующий код:</span><span class="sxs-lookup"><span data-stu-id="393d0-150">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="393d0-151">Измените строковые переменные для среды и параметров.</span><span class="sxs-lookup"><span data-stu-id="393d0-151">Edit the string variables for your environment and preferences.</span></span>  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="393d0-152">Создание асимметричного ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-152">Creating an Asymmetric Key</span></span>  
 <span data-ttu-id="393d0-153">Эта задача создает асимметричный ключ, который шифрует и расшифровывает ключ <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="393d0-153">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span> <span data-ttu-id="393d0-154">Этот ключ был использован для шифрования содержимого, и отображает имя контейнера ключей в элементе управления метки.</span><span class="sxs-lookup"><span data-stu-id="393d0-154">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="393d0-155">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Create Keys` (`buttonCreateAsmKeys_Click`).</span><span class="sxs-lookup"><span data-stu-id="393d0-155">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="393d0-156">Шифрование файла</span><span class="sxs-lookup"><span data-stu-id="393d0-156">Encrypting a File</span></span>  
 <span data-ttu-id="393d0-157">Эта задача включает в себя два метода: метод обработчика событий для `Encrypt File` кнопки (`buttonEncryptFile_Click`) и `EncryptFile` метод.</span><span class="sxs-lookup"><span data-stu-id="393d0-157">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="393d0-158">Первый метод отображает диалоговое окно для выбора файла и передает имя этого файла во второй метод, который выполняет шифрование.</span><span class="sxs-lookup"><span data-stu-id="393d0-158">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
 <span data-ttu-id="393d0-159">Зашифрованное содержимое, ключ и вектор инициализации сохраняются в один <xref:System.IO.FileStream>, который называется пакетом шифрования.</span><span class="sxs-lookup"><span data-stu-id="393d0-159">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
 <span data-ttu-id="393d0-160">Метод `EncryptFile` выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="393d0-160">The `EncryptFile` method does the following:</span></span>  
  
1.  <span data-ttu-id="393d0-161">Создает симметричный алгоритм <xref:System.Security.Cryptography.RijndaelManaged> для шифрования содержимого.</span><span class="sxs-lookup"><span data-stu-id="393d0-161">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to encrypt the content.</span></span>  
  
2.  <span data-ttu-id="393d0-162">Создает объект <xref:System.Security.Cryptography.RSACryptoServiceProvider> для шифрования ключа <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="393d0-162">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
3.  <span data-ttu-id="393d0-163">Использует объект <xref:System.Security.Cryptography.CryptoStream> для чтения и шифрования исходного файла <xref:System.IO.FileStream> блоками байтов в конечный объект <xref:System.IO.FileStream> для зашифрованного файла.</span><span class="sxs-lookup"><span data-stu-id="393d0-163">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4.  <span data-ttu-id="393d0-164">Определяет длину зашифрованного ключа и вектора инициализации и создает массивы байтов со значениями их длин.</span><span class="sxs-lookup"><span data-stu-id="393d0-164">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5.  <span data-ttu-id="393d0-165">Записывает ключ, вектор инициализации и значения их длин в зашифрованный пакет.</span><span class="sxs-lookup"><span data-stu-id="393d0-165">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="393d0-166">Пакет шифрования использует следующий формат:</span><span class="sxs-lookup"><span data-stu-id="393d0-166">The encryption package uses the following format:</span></span>  
  
-   <span data-ttu-id="393d0-167">Длина ключа, байты 0–3</span><span class="sxs-lookup"><span data-stu-id="393d0-167">Key length, bytes 0 - 3</span></span>  
  
-   <span data-ttu-id="393d0-168">Длина вектора инициализации, байты 4–7</span><span class="sxs-lookup"><span data-stu-id="393d0-168">IV length, bytes 4 - 7</span></span>  
  
-   <span data-ttu-id="393d0-169">Зашифрованный ключ</span><span class="sxs-lookup"><span data-stu-id="393d0-169">Encrypted key</span></span>  
  
-   <span data-ttu-id="393d0-170">Вектор инициализации</span><span class="sxs-lookup"><span data-stu-id="393d0-170">IV</span></span>  
  
-   <span data-ttu-id="393d0-171">Зашифрованный текст</span><span class="sxs-lookup"><span data-stu-id="393d0-171">Cipher text</span></span>  
  
 <span data-ttu-id="393d0-172">Вы можете использовать значения длины ключа и вектора инициализации для определения начальных точек и длин всех частей пакета шифрования, которые затем можно использовать для расшифровки файла.</span><span class="sxs-lookup"><span data-stu-id="393d0-172">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="393d0-173">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Encrypt File` (`buttonEncryptFile_Click`).</span><span class="sxs-lookup"><span data-stu-id="393d0-173">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="393d0-174">Добавьте следующий метод `EncryptFile` к форме:</span><span class="sxs-lookup"><span data-stu-id="393d0-174">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="393d0-175">Расшифровка файла</span><span class="sxs-lookup"><span data-stu-id="393d0-175">Decrypting a File</span></span>  
 <span data-ttu-id="393d0-176">Эта задача включает в себя два метода: метод обработчика событий для кнопки `Decrypt File` (`buttonDecryptFile_Click`) и метод `DecryptFile`.</span><span class="sxs-lookup"><span data-stu-id="393d0-176">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="393d0-177">Первый метод отображает диалоговое окно для выбора файла и передает имя этого файла во второй метод, который выполняет расшифровку.</span><span class="sxs-lookup"><span data-stu-id="393d0-177">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
 <span data-ttu-id="393d0-178">Метод `Decrypt` выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="393d0-178">The `Decrypt` method does the following:</span></span>  
  
1.  <span data-ttu-id="393d0-179">Создает симметричный алгоритм <xref:System.Security.Cryptography.RijndaelManaged> для расшифровки содержимого.</span><span class="sxs-lookup"><span data-stu-id="393d0-179">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to decrypt the content.</span></span>  
  
2.  <span data-ttu-id="393d0-180">Считывает первые восемь байтов <xref:System.IO.FileStream> зашифрованного пакета в массивы байтов, чтобы получить значения длин зашифрованного ключа и вектора инициализации.</span><span class="sxs-lookup"><span data-stu-id="393d0-180">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3.  <span data-ttu-id="393d0-181">Извлекает ключ и вектор инициализации из пакета шифрования в массивы байтов.</span><span class="sxs-lookup"><span data-stu-id="393d0-181">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4.  <span data-ttu-id="393d0-182">Создает объект <xref:System.Security.Cryptography.RSACryptoServiceProvider> для расшифровки ключа <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="393d0-182">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
5.  <span data-ttu-id="393d0-183">Использует объект <xref:System.Security.Cryptography.CryptoStream> для чтения и расшифровки зашифрованного текста пакета шифрования <xref:System.IO.FileStream> блоками байтов в объект <xref:System.IO.FileStream> для расшифрованного файла.</span><span class="sxs-lookup"><span data-stu-id="393d0-183">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="393d0-184">После завершения этой операции расшифровка завершается.</span><span class="sxs-lookup"><span data-stu-id="393d0-184">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="393d0-185">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Decrypt File`.</span><span class="sxs-lookup"><span data-stu-id="393d0-185">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="393d0-186">Добавьте следующий метод `DecryptFile` к форме:</span><span class="sxs-lookup"><span data-stu-id="393d0-186">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="393d0-187">Экспорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-187">Exporting a Public Key</span></span>  
 <span data-ttu-id="393d0-188">Эта задача сохраняет ключ, созданный при помощи кнопки `Create Keys`, в файл.</span><span class="sxs-lookup"><span data-stu-id="393d0-188">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="393d0-189">Она экспортирует только открытые параметры.</span><span class="sxs-lookup"><span data-stu-id="393d0-189">It exports only the public parameters.</span></span>  
  
 <span data-ttu-id="393d0-190">Данная задача имитирует ситуацию, в которой Ольга предоставляет Дмитрию свой открытый ключ, чтобы он мог зашифровывать для нее файлы.</span><span class="sxs-lookup"><span data-stu-id="393d0-190">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="393d0-191">Дмитрий и другие лица, имеющие этот открытый ключ, не смогут расшифровать данные, поскольку они не имеют полной пары ключей с закрытыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="393d0-191">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="393d0-192">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Export Public Key` (`buttonExportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="393d0-192">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="393d0-193">Импорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-193">Importing a Public Key</span></span>  
 <span data-ttu-id="393d0-194">Эта задача загружает ключ исключительно с открытыми параметрами, в том виде, в котором он был создан при помощи кнопки `Export Public Key`, и задает его в качестве имени контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="393d0-194">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
 <span data-ttu-id="393d0-195">Данная задача имитирует ситуацию, в которой Дмитрий загружает ключ Ольги исключительно с открытыми параметрами, чтобы зашифровывать для нее файлы.</span><span class="sxs-lookup"><span data-stu-id="393d0-195">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
 <span data-ttu-id="393d0-196">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Import Public Key` (`buttonImportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="393d0-196">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="393d0-197">Получение закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-197">Getting a Private Key</span></span>  
 <span data-ttu-id="393d0-198">Эта задача устанавливает в качестве имени контейнера ключей имя ключа, созданного при помощи кнопки `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="393d0-198">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="393d0-199">Контейнер ключей будет содержать полную пару ключей с закрытыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="393d0-199">The key container will contain the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="393d0-200">Данная задача имитирует ситуацию, в которой Ольга использует свой закрытый ключ для расшифровки файлов, зашифрованных Дмитрием.</span><span class="sxs-lookup"><span data-stu-id="393d0-200">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
 <span data-ttu-id="393d0-201">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Get Private Key` (`buttonGetPrivateKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="393d0-201">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="393d0-202">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="393d0-202">Testing the Application</span></span>  
 <span data-ttu-id="393d0-203">После сборки приложения необходимо выполнить следующие сценарии тестирования.</span><span class="sxs-lookup"><span data-stu-id="393d0-203">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="393d0-204">Создание ключей, шифрование и расшифровка</span><span class="sxs-lookup"><span data-stu-id="393d0-204">To create keys, encrypt, and decrypt</span></span>  
  
1.  <span data-ttu-id="393d0-205">Нажмите кнопку `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="393d0-205">Click the `Create Keys` button.</span></span> <span data-ttu-id="393d0-206">Метка отображает имя ключа и показывает, что это полная пара ключей.</span><span class="sxs-lookup"><span data-stu-id="393d0-206">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2.  <span data-ttu-id="393d0-207">Нажмите кнопку `Export Public Key`.</span><span class="sxs-lookup"><span data-stu-id="393d0-207">Click the `Export Public Key` button.</span></span> <span data-ttu-id="393d0-208">Обратите внимание, что при экспорте параметров открытого ключа текущий ключ не изменяется.</span><span class="sxs-lookup"><span data-stu-id="393d0-208">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3.  <span data-ttu-id="393d0-209">Нажмите кнопку `Encrypt File` и выберите файл.</span><span class="sxs-lookup"><span data-stu-id="393d0-209">Click the `Encrypt File` button and select a file.</span></span>  
  
4.  <span data-ttu-id="393d0-210">Нажмите кнопку `Decrypt File` и выберите только что зашифрованный файл.</span><span class="sxs-lookup"><span data-stu-id="393d0-210">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5.  <span data-ttu-id="393d0-211">Изучите только что расшифрованный файл.</span><span class="sxs-lookup"><span data-stu-id="393d0-211">Examine the file just decrypted.</span></span>  
  
6.  <span data-ttu-id="393d0-212">Закройте приложение и перезапустите его, чтобы протестировать извлечение сохраненных контейнеров ключей в следующем сценарии.</span><span class="sxs-lookup"><span data-stu-id="393d0-212">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="393d0-213">Шифрование при помощи открытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-213">To encrypt using the public key</span></span>  
  
1.  <span data-ttu-id="393d0-214">Нажмите кнопку `Import Public Key`.</span><span class="sxs-lookup"><span data-stu-id="393d0-214">Click the `Import Public Key` button.</span></span> <span data-ttu-id="393d0-215">Метка отображает имя ключа и показывает, что это только открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="393d0-215">The label displays the key name and shows that it is public only.</span></span>  
  
2.  <span data-ttu-id="393d0-216">Нажмите кнопку `Encrypt File` и выберите файл.</span><span class="sxs-lookup"><span data-stu-id="393d0-216">Click the `Encrypt File` button and select a file.</span></span>  
  
3.  <span data-ttu-id="393d0-217">Нажмите кнопку `Decrypt File` и выберите только что зашифрованный файл.</span><span class="sxs-lookup"><span data-stu-id="393d0-217">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="393d0-218">Произойдет сбой, так как для расшифровки нужен закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="393d0-218">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="393d0-219">Этот сценарий показывает, как шифровать файлы для другого лица при наличии только открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="393d0-219">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="393d0-220">Обычно это лицо предоставляет вам только открытый ключ и утаивает закрытый ключ для расшифровки.</span><span class="sxs-lookup"><span data-stu-id="393d0-220">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="393d0-221">Расшифровка при помощи закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="393d0-221">To decrypt using the private key</span></span>  
  
1.  <span data-ttu-id="393d0-222">Нажмите кнопку `Get Private Key`.</span><span class="sxs-lookup"><span data-stu-id="393d0-222">Click the `Get Private Key` button.</span></span> <span data-ttu-id="393d0-223">Метка отображает имя ключа и показывает, имеется ли полная пара ключей.</span><span class="sxs-lookup"><span data-stu-id="393d0-223">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2.  <span data-ttu-id="393d0-224">Нажмите кнопку `Decrypt File` и выберите только что зашифрованный файл.</span><span class="sxs-lookup"><span data-stu-id="393d0-224">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="393d0-225">Эта операция будет успешной, так как имеется полная пара ключей для расшифровки.</span><span class="sxs-lookup"><span data-stu-id="393d0-225">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="393d0-226">См. также</span><span class="sxs-lookup"><span data-stu-id="393d0-226">See Also</span></span>  
 [<span data-ttu-id="393d0-227">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="393d0-227">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
