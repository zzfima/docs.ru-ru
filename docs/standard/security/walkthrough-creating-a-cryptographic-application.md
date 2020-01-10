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
# <a name="walkthrough-creating-a-cryptographic-application"></a>Пошаговое руководство. Создание криптографического приложения
В этом пошаговом руководстве показано, как зашифровать и расшифровать содержимое. Пример кода предназначен для приложения Windows Forms. Это приложение не демонстрирует реальные сценарии, такие как использование смарт-карт. Вместо этого оно демонстрирует основные принципы шифрования и расшифровки.  
  
 В этом пошаговом руководстве использует следующие правила шифрования:  
  
- Используйте класс <xref:System.Security.Cryptography.RijndaelManaged> с симметричным алгоритмом для шифрования и расшифровки данных при помощи автоматически созданных <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> и <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.  
  
- Используйте <xref:System.Security.Cryptography.RSACryptoServiceProvider> с асимметричным алгоритмом для шифрования и расшифровки ключа для данных, зашифрованных при помощи <xref:System.Security.Cryptography.RijndaelManaged>. Асимметричные алгоритмы лучше подходят для небольших объемов данных, таких как ключ.  
  
    > [!NOTE]
    > Если вы хотите защитить данные на компьютере, а не обмениваться зашифрованным содержимым с другими людьми, рекомендуется использовать классы <xref:System.Security.Cryptography.ProtectedData> или <xref:System.Security.Cryptography.ProtectedMemory>.  
  
 В следующей таблице указаны задачи шифрования из этого раздела.  
  
|Задача|Описание|  
|----------|-----------------|  
|Создание приложения Windows Forms|Выводит список элементов управления, необходимых для запуска приложения.|  
|Объявление глобальных объектов|Объявляет, что строковые переменные пути <xref:System.Security.Cryptography.CspParameters> и <xref:System.Security.Cryptography.RSACryptoServiceProvider> имеют глобальный контекст класса <xref:System.Windows.Forms.Form>.|  
|Создание асимметричного ключа|Создает пару значений открытого и закрытого асимметричного ключа и присваивает ей имя контейнера ключей.|  
|Шифрование файла|Отображает диалоговое окно, где можно выбрать шифруемый файл, и шифрует этот файл.|  
|Расшифровка файла|Отображает диалоговое окно, где можно выбрать зашифрованный файл, и выполняет расшифровку этого файла.|  
|Получение закрытого ключа|Возвращает полную пару ключей при помощи имени контейнера ключей.|  
|Экспорт открытого ключа|Сохраняет ключ в XML-файл только с открытыми параметрами.|  
|Импорт открытого ключа|Загружает ключ из XML-файла в контейнер ключей.|  
|Тестирование приложения|Список процедур для тестирования этого приложения.|  
  
## <a name="prerequisites"></a>Prerequisites  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
- Ссылки на пространства имен <xref:System.IO> и <xref:System.Security.Cryptography>.  
  
## <a name="creating-a-windows-forms-application"></a>Создание приложения Windows Forms  
 Большинство примеров кода в этом пошаговом руководстве предназначено для использования в качестве обработчиков событий для элементов управления кнопок. В следующей таблице перечислены элементы управления, необходимые для образца приложения, и их имена в соответствии с примерами кода.  
  
|Элемент управления|Name|Текстовое свойство (при необходимости)|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|Шифрование файла|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|Расшифровка файла|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|Создание ключей|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|Экспорт открытого ключа|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|Импорт открытого ключа|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|Получение закрытого ключа|  
|<xref:System.Windows.Forms.Label>|`label1`|Ключ не задан|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 Дважды щелкните кнопки в конструкторе Visual Studio, чтобы создать для них обработчики событий.  
  
## <a name="declaring-global-objects"></a>Объявление глобальных объектов  
 Добавьте в конструктор формы следующий код: Измените строковые переменные для среды и параметров.  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a>Создание асимметричного ключа  
 Эта задача создает асимметричный ключ, который шифрует и расшифровывает ключ <xref:System.Security.Cryptography.RijndaelManaged>. Этот ключ был использован для шифрования содержимого, и отображает имя контейнера ключей в элементе управления метки.  
  
 Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Create Keys` (`buttonCreateAsmKeys_Click`).  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a>Шифрование файла  
 Эта задача состоит из двух методов: метода обработчика событий для кнопки `Encrypt File` (`buttonEncryptFile_Click`) и метода `EncryptFile`. Первый метод отображает диалоговое окно для выбора файла и передает имя этого файла во второй метод, который выполняет шифрование.  
  
 Зашифрованное содержимое, ключ и вектор инициализации сохраняются в один <xref:System.IO.FileStream>, который называется пакетом шифрования.  
  
 Метод `EncryptFile` выполняет следующие действия:  
  
1. Создает симметричный алгоритм <xref:System.Security.Cryptography.RijndaelManaged> для шифрования содержимого.  
  
2. Создает объект <xref:System.Security.Cryptography.RSACryptoServiceProvider> для шифрования ключа <xref:System.Security.Cryptography.RijndaelManaged>.  
  
3. Использует объект <xref:System.Security.Cryptography.CryptoStream> для чтения и шифрования исходного файла <xref:System.IO.FileStream> блоками байтов в конечный объект <xref:System.IO.FileStream> для зашифрованного файла.  
  
4. Определяет длину зашифрованного ключа и вектора инициализации и создает массивы байтов со значениями их длин.  
  
5. Записывает ключ, вектор инициализации и значения их длин в зашифрованный пакет.  
  
 Пакет шифрования использует следующий формат:  
  
- Длина ключа, байты 0–3  
  
- Длина вектора инициализации, байты 4–7  
  
- Зашифрованный ключ  
  
- Вектор инициализации  
  
- Зашифрованный текст  
  
 Вы можете использовать значения длины ключа и вектора инициализации для определения начальных точек и длин всех частей пакета шифрования, которые затем можно использовать для расшифровки файла.  
  
 Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Encrypt File` (`buttonEncryptFile_Click`).  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 Добавьте следующий метод `EncryptFile` к форме:  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a>Расшифровка файла  
 Эта задача включает в себя два метода: метод обработчика событий для кнопки `Decrypt File` (`buttonDecryptFile_Click`) и метод `DecryptFile`. Первый метод отображает диалоговое окно для выбора файла и передает имя этого файла во второй метод, который выполняет расшифровку.  
  
 Метод `Decrypt` выполняет следующие действия:  
  
1. Создает симметричный алгоритм <xref:System.Security.Cryptography.RijndaelManaged> для расшифровки содержимого.  
  
2. Считывает первые восемь байтов <xref:System.IO.FileStream> зашифрованного пакета в массивы байтов, чтобы получить значения длин зашифрованного ключа и вектора инициализации.  
  
3. Извлекает ключ и вектор инициализации из пакета шифрования в массивы байтов.  
  
4. Создает объект <xref:System.Security.Cryptography.RSACryptoServiceProvider> для расшифровки ключа <xref:System.Security.Cryptography.RijndaelManaged>.  
  
5. Использует объект <xref:System.Security.Cryptography.CryptoStream> для чтения и расшифровки зашифрованного текста пакета шифрования <xref:System.IO.FileStream> блоками байтов в объект <xref:System.IO.FileStream> для расшифрованного файла. После завершения этой операции расшифровка завершается.  
  
 Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Decrypt File`.  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 Добавьте следующий метод `DecryptFile` к форме:  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a>Экспорт открытого ключа  
 Эта задача сохраняет ключ, созданный при помощи кнопки `Create Keys`, в файл. Она экспортирует только открытые параметры.  
  
 Данная задача имитирует ситуацию, в которой Ольга предоставляет Дмитрию свой открытый ключ, чтобы он мог зашифровывать для нее файлы. Дмитрий и другие лица, имеющие этот открытый ключ, не смогут расшифровать данные, поскольку они не имеют полной пары ключей с закрытыми параметрами.  
  
 Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Export Public Key` (`buttonExportPublicKey_Click`).  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a>Импорт открытого ключа  
 Эта задача загружает ключ исключительно с открытыми параметрами, в том виде, в котором он был создан при помощи кнопки `Export Public Key`, и задает его в качестве имени контейнера ключей.  
  
 Данная задача имитирует ситуацию, в которой Дмитрий загружает ключ Ольги исключительно с открытыми параметрами, чтобы зашифровывать для нее файлы.  
  
 Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Import Public Key` (`buttonImportPublicKey_Click`).  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a>Получение закрытого ключа  
 Эта задача устанавливает в качестве имени контейнера ключей имя ключа, созданного при помощи кнопки `Create Keys`. Контейнер ключей будет содержать полную пару ключей с закрытыми параметрами.  
  
 Данная задача имитирует ситуацию, в которой Ольга использует свой закрытый ключ для расшифровки файлов, зашифрованных Дмитрием.  
  
 Добавьте следующий код в качестве обработчика событий `Click` для кнопки `Get Private Key` (`buttonGetPrivateKey_Click`).  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 После сборки приложения необходимо выполнить следующие сценарии тестирования.  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a>Создание ключей, шифрование и расшифровка  
  
1. Нажмите кнопку `Create Keys`. Метка отображает имя ключа и показывает, что это полная пара ключей.  
  
2. Нажмите кнопку `Export Public Key`. Обратите внимание, что при экспорте параметров открытого ключа текущий ключ не изменяется.  
  
3. Нажмите кнопку `Encrypt File` и выберите файл.  
  
4. Нажмите кнопку `Decrypt File` и выберите только что зашифрованный файл.  
  
5. Изучите только что расшифрованный файл.  
  
6. Закройте приложение и перезапустите его, чтобы протестировать извлечение сохраненных контейнеров ключей в следующем сценарии.  
  
#### <a name="to-encrypt-using-the-public-key"></a>Шифрование при помощи открытого ключа  
  
1. Нажмите кнопку `Import Public Key`. Метка отображает имя ключа и показывает, что это только открытый ключ.  
  
2. Нажмите кнопку `Encrypt File` и выберите файл.  
  
3. Нажмите кнопку `Decrypt File` и выберите только что зашифрованный файл. Произойдет сбой, так как для расшифровки нужен закрытый ключ.  
  
 Этот сценарий показывает, как шифровать файлы для другого лица при наличии только открытого ключа. Обычно это лицо предоставляет вам только открытый ключ и утаивает закрытый ключ для расшифровки.  
  
#### <a name="to-decrypt-using-the-private-key"></a>Расшифровка при помощи закрытого ключа  
  
1. Нажмите кнопку `Get Private Key`. Метка отображает имя ключа и показывает, имеется ли полная пара ключей.  
  
2. Нажмите кнопку `Decrypt File` и выберите только что зашифрованный файл. Эта операция будет успешной, так как имеется полная пара ключей для расшифровки.  
  
## <a name="see-also"></a>См. также:

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
