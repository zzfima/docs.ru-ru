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
ms.openlocfilehash: 6e2d9b8bebdfd2ea5d5507cc73d444fa8bf785fb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705838"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="ae8f8-102">Пошаговое руководство. Создание криптографического приложения</span><span class="sxs-lookup"><span data-stu-id="ae8f8-102">Walkthrough: Creating a Cryptographic Application</span></span>
<span data-ttu-id="ae8f8-103">В этом пошаговом руководстве показано, как зашифровать и расшифровать содержимое.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-103">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="ae8f8-104">Пример кода предназначен для приложения Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-104">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="ae8f8-105">Это приложение не демонстрирует реальные сценарии, такие как использование смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-105">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="ae8f8-106">Вместо этого оно демонстрирует основные принципы шифрования и расшифровки.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-106">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
 <span data-ttu-id="ae8f8-107">В этом пошаговом руководстве использует следующие правила шифрования:</span><span class="sxs-lookup"><span data-stu-id="ae8f8-107">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="ae8f8-108">Используйте класс <xref:System.Security.Cryptography.RijndaelManaged> с симметричным алгоритмом для шифрования и расшифровки данных при помощи автоматически созданных <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> и <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-108">Use the <xref:System.Security.Cryptography.RijndaelManaged> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="ae8f8-109">Используйте <xref:System.Security.Cryptography.RSACryptoServiceProvider> с асимметричным алгоритмом для шифрования и расшифровки ключа для данных, зашифрованных при помощи <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-109">Use the <xref:System.Security.Cryptography.RSACryptoServiceProvider>, an asymmetric algorithm, to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.RijndaelManaged>.</span></span> <span data-ttu-id="ae8f8-110">Асимметричные алгоритмы лучше подходят для небольших объемов данных, таких как ключ.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-110">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ae8f8-111">Если вы хотите защитить данные на компьютере, а не обмениваться зашифрованным содержимым с другими людьми, рекомендуется использовать классы <xref:System.Security.Cryptography.ProtectedData> или <xref:System.Security.Cryptography.ProtectedMemory>.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-111">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> or <xref:System.Security.Cryptography.ProtectedMemory> classes.</span></span>  
  
 <span data-ttu-id="ae8f8-112">В следующей таблице указаны задачи шифрования из этого раздела.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-112">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="ae8f8-113">Задача</span><span class="sxs-lookup"><span data-stu-id="ae8f8-113">Task</span></span>|<span data-ttu-id="ae8f8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ae8f8-114">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ae8f8-115">Создание приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae8f8-115">Creating a Windows Forms application</span></span>|<span data-ttu-id="ae8f8-116">Выводит список элементов управления, необходимых для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-116">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="ae8f8-117">Объявление глобальных объектов</span><span class="sxs-lookup"><span data-stu-id="ae8f8-117">Declaring global objects</span></span>|<span data-ttu-id="ae8f8-118">Объявляет, что строковые переменные пути <xref:System.Security.Cryptography.CspParameters> и <xref:System.Security.Cryptography.RSACryptoServiceProvider> имеют глобальный контекст класса <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-118">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="ae8f8-119">Создание асимметричного ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-119">Creating an asymmetric key</span></span>|<span data-ttu-id="ae8f8-120">Создает пару значений открытого и закрытого асимметричного ключа и присваивает ей имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-120">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="ae8f8-121">Шифрование файла</span><span class="sxs-lookup"><span data-stu-id="ae8f8-121">Encrypting a file</span></span>|<span data-ttu-id="ae8f8-122">Отображает диалоговое окно, где можно выбрать шифруемый файл, и шифрует этот файл.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-122">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="ae8f8-123">Расшифровка файла</span><span class="sxs-lookup"><span data-stu-id="ae8f8-123">Decrypting a file</span></span>|<span data-ttu-id="ae8f8-124">Отображает диалоговое окно, где можно выбрать зашифрованный файл, и выполняет расшифровку этого файла.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-124">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="ae8f8-125">Получение закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-125">Getting a private key</span></span>|<span data-ttu-id="ae8f8-126">Возвращает полную пару ключей при помощи имени контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-126">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="ae8f8-127">Экспорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-127">Exporting a public key</span></span>|<span data-ttu-id="ae8f8-128">Сохраняет ключ в XML-файл только с открытыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-128">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="ae8f8-129">Импорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-129">Importing a public key</span></span>|<span data-ttu-id="ae8f8-130">Загружает ключ из XML-файла в контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-130">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="ae8f8-131">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="ae8f8-131">Testing the application</span></span>|<span data-ttu-id="ae8f8-132">Список процедур для тестирования этого приложения.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-132">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="ae8f8-133">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="ae8f8-133">Prerequisites</span></span>  
 <span data-ttu-id="ae8f8-134">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-134">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="ae8f8-135">Ссылки на пространства имен <xref:System.IO> и <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-135">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="ae8f8-136">Создание приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae8f8-136">Creating a Windows Forms Application</span></span>  
 <span data-ttu-id="ae8f8-137">Большинство примеров кода в этом пошаговом руководстве предназначено для использования в качестве обработчиков событий для элементов управления кнопок.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-137">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="ae8f8-138">В следующей таблице перечислены элементы управления, необходимые для образца приложения, и их имена в соответствии с примерами кода.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-138">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="ae8f8-139">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="ae8f8-139">Control</span></span>|<span data-ttu-id="ae8f8-140">Name</span><span class="sxs-lookup"><span data-stu-id="ae8f8-140">Name</span></span>|<span data-ttu-id="ae8f8-141">Текстовое свойство (при необходимости)</span><span class="sxs-lookup"><span data-stu-id="ae8f8-141">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="ae8f8-142">Шифрование файла</span><span class="sxs-lookup"><span data-stu-id="ae8f8-142">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="ae8f8-143">Расшифровка файла</span><span class="sxs-lookup"><span data-stu-id="ae8f8-143">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="ae8f8-144">Создание ключей</span><span class="sxs-lookup"><span data-stu-id="ae8f8-144">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="ae8f8-145">Экспорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-145">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="ae8f8-146">Импорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-146">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="ae8f8-147">Получение закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-147">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="ae8f8-148">Ключ не задан</span><span class="sxs-lookup"><span data-stu-id="ae8f8-148">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="ae8f8-149">Дважды щелкните кнопки в конструкторе Visual Studio, чтобы создать для них обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-149">Double-click the buttons in the  Visual Studio designer to create their event handlers.</span></span>  
  
## <a name="declaring-global-objects"></a><span data-ttu-id="ae8f8-150">Объявление глобальных объектов</span><span class="sxs-lookup"><span data-stu-id="ae8f8-150">Declaring Global Objects</span></span>  
 <span data-ttu-id="ae8f8-151">Добавьте в конструктор формы следующий код:</span><span class="sxs-lookup"><span data-stu-id="ae8f8-151">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="ae8f8-152">Измените строковые переменные для среды и параметров.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-152">Edit the string variables for your environment and preferences.</span></span>  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="ae8f8-153">Создание асимметричного ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-153">Creating an Asymmetric Key</span></span>  
 <span data-ttu-id="ae8f8-154">Эта задача создает асимметричный ключ, который шифрует и расшифровывает ключ <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-154">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span> <span data-ttu-id="ae8f8-155">Этот ключ был использован для шифрования содержимого, и отображает имя контейнера ключей в элементе управления метки.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-155">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="ae8f8-156">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Create Keys` (`buttonCreateAsmKeys_Click`).</span><span class="sxs-lookup"><span data-stu-id="ae8f8-156">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="ae8f8-157">Шифрование файла</span><span class="sxs-lookup"><span data-stu-id="ae8f8-157">Encrypting a File</span></span>  
 <span data-ttu-id="ae8f8-158">Эта задача состоит из двух методов: метода обработчика событий для кнопки `Encrypt File` (`buttonEncryptFile_Click`) и метода `EncryptFile`.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-158">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="ae8f8-159">Первый метод отображает диалоговое окно для выбора файла и передает имя этого файла во второй метод, который выполняет шифрование.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-159">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
 <span data-ttu-id="ae8f8-160">Зашифрованное содержимое, ключ и вектор инициализации сохраняются в один <xref:System.IO.FileStream>, который называется пакетом шифрования.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-160">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
 <span data-ttu-id="ae8f8-161">Метод `EncryptFile` выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ae8f8-161">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="ae8f8-162">Создает симметричный алгоритм <xref:System.Security.Cryptography.RijndaelManaged> для шифрования содержимого.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-162">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="ae8f8-163">Создает объект <xref:System.Security.Cryptography.RSACryptoServiceProvider> для шифрования ключа <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-163">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
3. <span data-ttu-id="ae8f8-164">Использует объект <xref:System.Security.Cryptography.CryptoStream> для чтения и шифрования исходного файла <xref:System.IO.FileStream> блоками байтов в конечный объект <xref:System.IO.FileStream> для зашифрованного файла.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-164">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="ae8f8-165">Определяет длину зашифрованного ключа и вектора инициализации и создает массивы байтов со значениями их длин.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-165">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="ae8f8-166">Записывает ключ, вектор инициализации и значения их длин в зашифрованный пакет.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-166">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="ae8f8-167">Пакет шифрования использует следующий формат:</span><span class="sxs-lookup"><span data-stu-id="ae8f8-167">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="ae8f8-168">Длина ключа, байты 0–3</span><span class="sxs-lookup"><span data-stu-id="ae8f8-168">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="ae8f8-169">Длина вектора инициализации, байты 4–7</span><span class="sxs-lookup"><span data-stu-id="ae8f8-169">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="ae8f8-170">Зашифрованный ключ</span><span class="sxs-lookup"><span data-stu-id="ae8f8-170">Encrypted key</span></span>  
  
- <span data-ttu-id="ae8f8-171">Вектор инициализации</span><span class="sxs-lookup"><span data-stu-id="ae8f8-171">IV</span></span>  
  
- <span data-ttu-id="ae8f8-172">Зашифрованный текст</span><span class="sxs-lookup"><span data-stu-id="ae8f8-172">Cipher text</span></span>  
  
 <span data-ttu-id="ae8f8-173">Вы можете использовать значения длины ключа и вектора инициализации для определения начальных точек и длин всех частей пакета шифрования, которые затем можно использовать для расшифровки файла.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-173">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="ae8f8-174">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Encrypt File` (`buttonEncryptFile_Click`).</span><span class="sxs-lookup"><span data-stu-id="ae8f8-174">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="ae8f8-175">Добавьте следующий метод `EncryptFile` к форме:</span><span class="sxs-lookup"><span data-stu-id="ae8f8-175">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="ae8f8-176">Расшифровка файла</span><span class="sxs-lookup"><span data-stu-id="ae8f8-176">Decrypting a File</span></span>  
 <span data-ttu-id="ae8f8-177">Эта задача включает в себя два метода: метод обработчика событий для кнопки `Decrypt File` (`buttonDecryptFile_Click`) и метод `DecryptFile`.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-177">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="ae8f8-178">Первый метод отображает диалоговое окно для выбора файла и передает имя этого файла во второй метод, который выполняет расшифровку.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-178">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
 <span data-ttu-id="ae8f8-179">Метод `Decrypt` выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ae8f8-179">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="ae8f8-180">Создает симметричный алгоритм <xref:System.Security.Cryptography.RijndaelManaged> для расшифровки содержимого.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-180">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="ae8f8-181">Считывает первые восемь байтов <xref:System.IO.FileStream> зашифрованного пакета в массивы байтов, чтобы получить значения длин зашифрованного ключа и вектора инициализации.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-181">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="ae8f8-182">Извлекает ключ и вектор инициализации из пакета шифрования в массивы байтов.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-182">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="ae8f8-183">Создает объект <xref:System.Security.Cryptography.RSACryptoServiceProvider> для расшифровки ключа <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-183">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
5. <span data-ttu-id="ae8f8-184">Использует объект <xref:System.Security.Cryptography.CryptoStream> для чтения и расшифровки зашифрованного текста пакета шифрования <xref:System.IO.FileStream> блоками байтов в объект <xref:System.IO.FileStream> для расшифрованного файла.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-184">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="ae8f8-185">После завершения этой операции расшифровка завершается.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-185">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="ae8f8-186">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Decrypt File`.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-186">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="ae8f8-187">Добавьте следующий метод `DecryptFile` к форме:</span><span class="sxs-lookup"><span data-stu-id="ae8f8-187">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="ae8f8-188">Экспорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-188">Exporting a Public Key</span></span>  
 <span data-ttu-id="ae8f8-189">Эта задача сохраняет ключ, созданный при помощи кнопки `Create Keys`, в файл.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-189">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="ae8f8-190">Она экспортирует только открытые параметры.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-190">It exports only the public parameters.</span></span>  
  
 <span data-ttu-id="ae8f8-191">Данная задача имитирует ситуацию, в которой Ольга предоставляет Дмитрию свой открытый ключ, чтобы он мог зашифровывать для нее файлы.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-191">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="ae8f8-192">Дмитрий и другие лица, имеющие этот открытый ключ, не смогут расшифровать данные, поскольку они не имеют полной пары ключей с закрытыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-192">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="ae8f8-193">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Export Public Key` (`buttonExportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="ae8f8-193">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="ae8f8-194">Импорт открытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-194">Importing a Public Key</span></span>  
 <span data-ttu-id="ae8f8-195">Эта задача загружает ключ исключительно с открытыми параметрами, в том виде, в котором он был создан при помощи кнопки `Export Public Key`, и задает его в качестве имени контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-195">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
 <span data-ttu-id="ae8f8-196">Данная задача имитирует ситуацию, в которой Дмитрий загружает ключ Ольги исключительно с открытыми параметрами, чтобы зашифровывать для нее файлы.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-196">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
 <span data-ttu-id="ae8f8-197">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Import Public Key` (`buttonImportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="ae8f8-197">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="ae8f8-198">Получение закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-198">Getting a Private Key</span></span>  
 <span data-ttu-id="ae8f8-199">Эта задача устанавливает в качестве имени контейнера ключей имя ключа, созданного при помощи кнопки `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-199">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="ae8f8-200">Контейнер ключей будет содержать полную пару ключей с закрытыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-200">The key container will contain the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="ae8f8-201">Данная задача имитирует ситуацию, в которой Ольга использует свой закрытый ключ для расшифровки файлов, зашифрованных Дмитрием.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-201">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
 <span data-ttu-id="ae8f8-202">Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Get Private Key` (`buttonGetPrivateKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="ae8f8-202">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="ae8f8-203">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="ae8f8-203">Testing the Application</span></span>  
 <span data-ttu-id="ae8f8-204">После сборки приложения необходимо выполнить следующие сценарии тестирования.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-204">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="ae8f8-205">Создание ключей, шифрование и расшифровка</span><span class="sxs-lookup"><span data-stu-id="ae8f8-205">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="ae8f8-206">Нажмите кнопку `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-206">Click the `Create Keys` button.</span></span> <span data-ttu-id="ae8f8-207">Метка отображает имя ключа и показывает, что это полная пара ключей.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-207">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="ae8f8-208">Нажмите кнопку `Export Public Key`.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-208">Click the `Export Public Key` button.</span></span> <span data-ttu-id="ae8f8-209">Обратите внимание, что при экспорте параметров открытого ключа текущий ключ не изменяется.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-209">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="ae8f8-210">Нажмите кнопку `Encrypt File` и выберите файл.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-210">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="ae8f8-211">Нажмите кнопку `Decrypt File` и выберите только что зашифрованный файл.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-211">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="ae8f8-212">Изучите только что расшифрованный файл.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-212">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="ae8f8-213">Закройте приложение и перезапустите его, чтобы протестировать извлечение сохраненных контейнеров ключей в следующем сценарии.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-213">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="ae8f8-214">Шифрование при помощи открытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-214">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="ae8f8-215">Нажмите кнопку `Import Public Key`.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-215">Click the `Import Public Key` button.</span></span> <span data-ttu-id="ae8f8-216">Метка отображает имя ключа и показывает, что это только открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-216">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="ae8f8-217">Нажмите кнопку `Encrypt File` и выберите файл.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-217">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="ae8f8-218">Нажмите кнопку `Decrypt File` и выберите только что зашифрованный файл.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-218">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="ae8f8-219">Произойдет сбой, так как для расшифровки нужен закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-219">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="ae8f8-220">Этот сценарий показывает, как шифровать файлы для другого лица при наличии только открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-220">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="ae8f8-221">Обычно это лицо предоставляет вам только открытый ключ и утаивает закрытый ключ для расшифровки.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-221">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="ae8f8-222">Расшифровка при помощи закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="ae8f8-222">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="ae8f8-223">Нажмите кнопку `Get Private Key`.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-223">Click the `Get Private Key` button.</span></span> <span data-ttu-id="ae8f8-224">Метка отображает имя ключа и показывает, имеется ли полная пара ключей.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-224">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="ae8f8-225">Нажмите кнопку `Decrypt File` и выберите только что зашифрованный файл.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-225">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="ae8f8-226">Эта операция будет успешной, так как имеется полная пара ключей для расшифровки.</span><span class="sxs-lookup"><span data-stu-id="ae8f8-226">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8f8-227">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae8f8-227">See also</span></span>

- [<span data-ttu-id="ae8f8-228">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="ae8f8-228">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
