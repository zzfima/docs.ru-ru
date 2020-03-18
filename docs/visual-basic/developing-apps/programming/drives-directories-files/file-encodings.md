---
title: Кодировки файлов
ms.date: 07/20/2015
helpviewer_keywords:
- character encodings
- files [Visual Basic], encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
ms.openlocfilehash: 52770187568d0ba0f54ec36ee2c3d754a9b4d9a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348883"
---
# <a name="file-encodings-visual-basic"></a><span data-ttu-id="426c3-102">Кодировки файлов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="426c3-102">File Encodings (Visual Basic)</span></span>

<span data-ttu-id="426c3-103">Кодировки файлов (или кодировки символов) определяют отображение символов при обработке текстов.</span><span class="sxs-lookup"><span data-stu-id="426c3-103">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="426c3-104">Одна кодировка может быть предпочтительнее другой с точки зрения возможности или невозможности оперирования языковыми символами, хотя обычно предпочитается Юникод.</span><span class="sxs-lookup"><span data-stu-id="426c3-104">One encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span>

<span data-ttu-id="426c3-105">При чтении или записи в файлы несоответствие кодировок файлов может привести к исключениям или неверным результатам.</span><span class="sxs-lookup"><span data-stu-id="426c3-105">When reading from or writing to files, improperly matching file encodings may result in exceptions or incorrect results.</span></span>

## <a name="types-of-encodings"></a><span data-ttu-id="426c3-106">Типы кодировок</span><span class="sxs-lookup"><span data-stu-id="426c3-106">Types of Encodings</span></span>

<span data-ttu-id="426c3-107">Юникод является предпочтительной кодировкой при работе с файлами.</span><span class="sxs-lookup"><span data-stu-id="426c3-107">Unicode is the preferred encoding when working with files.</span></span> <span data-ttu-id="426c3-108">Юникод — мировой стандарт кодировки символов, в котором используются 16-разрядные кодовые значения для представления всех символов, используемых в современных вычислениях, включая технические символы и специальные символы, используемые в издательском деле.</span><span class="sxs-lookup"><span data-stu-id="426c3-108">Unicode is a worldwide character-encoding standard that uses 16-bit code values to represent all the characters used in modern computing, including technical symbols and special characters used in publishing.</span></span>

<span data-ttu-id="426c3-109">Предыдущие стандарты кодировок состояли из традиционных наборов знаков, таких как набор знаков ANSI Windows, использующий 8-разрядные кодовые значения, или комбинаций из 8-разрядных кодовых значений для представления символов, используемых в конкретном языке или географическом регионе.</span><span class="sxs-lookup"><span data-stu-id="426c3-109">Previous character-encoding standards consisted of traditional character sets, such as the Windows ANSI character set that uses 8-bit code values, or combinations of 8-bit values, to represent the characters used in a specific language or geographical region.</span></span>

## <a name="encoding-class"></a><span data-ttu-id="426c3-110">Класс Encoding</span><span class="sxs-lookup"><span data-stu-id="426c3-110">Encoding Class</span></span>

<span data-ttu-id="426c3-111">Класс <xref:System.Text.Encoding> представляет кодировку символов.</span><span class="sxs-lookup"><span data-stu-id="426c3-111">The <xref:System.Text.Encoding> class represents a character encoding.</span></span> <span data-ttu-id="426c3-112">В этой таблице перечислены типы доступных кодировок и дано их описание.</span><span class="sxs-lookup"><span data-stu-id="426c3-112">This table lists the type of encodings available and describes each.</span></span>

|<span data-ttu-id="426c3-113">Имя</span><span class="sxs-lookup"><span data-stu-id="426c3-113">Name</span></span>|<span data-ttu-id="426c3-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="426c3-114">Description</span></span>|
|---|---|
|<xref:System.Text.ASCIIEncoding>|<span data-ttu-id="426c3-115">Представляет кодировку ASCII символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="426c3-115">Represents an ASCII character encoding of Unicode characters.</span></span>|
|<xref:System.Text.UnicodeEncoding>|<span data-ttu-id="426c3-116">Представляет кодировку символов Юникода в формате UTF-16.</span><span class="sxs-lookup"><span data-stu-id="426c3-116">Represents a UTF-16 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF32Encoding>|<span data-ttu-id="426c3-117">Представляет кодировку символов Юникода в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="426c3-117">Represents a UTF-32 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF7Encoding>|<span data-ttu-id="426c3-118">Представляет кодировку UTF-7 символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="426c3-118">Represents a UTF-7 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF8Encoding>|<span data-ttu-id="426c3-119">Представляет кодировку символов Юникода в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="426c3-119">Represents a UTF-8 encoding of Unicode characters.</span></span>|

## <a name="see-also"></a><span data-ttu-id="426c3-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="426c3-120">See also</span></span>

- [<span data-ttu-id="426c3-121">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="426c3-121">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="426c3-122">Запись в файлы</span><span class="sxs-lookup"><span data-stu-id="426c3-122">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
