---
title: Коллекции схемы ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365910"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="3ac25-102">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="3ac25-102">ODBC Schema Collections</span></span>

<span data-ttu-id="3ac25-103">В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="3ac25-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="3ac25-104">Драйвер ODBC для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ac25-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="3ac25-105">Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="3ac25-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="3ac25-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="3ac25-106">Tables</span></span>

- <span data-ttu-id="3ac25-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="3ac25-107">Indexes</span></span>

- <span data-ttu-id="3ac25-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="3ac25-108">Columns</span></span>

- <span data-ttu-id="3ac25-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3ac25-109">Procedures</span></span>

- <span data-ttu-id="3ac25-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3ac25-110">ProcedureColumns</span></span>

- <span data-ttu-id="3ac25-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3ac25-111">ProcedureParameters</span></span>

- <span data-ttu-id="3ac25-112">Представления</span><span class="sxs-lookup"><span data-stu-id="3ac25-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="3ac25-113">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="3ac25-113">Tables and Views</span></span>

|<span data-ttu-id="3ac25-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-114">ColumnName</span></span>|<span data-ttu-id="3ac25-115">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="3ac25-116">TABLE_CAT</span></span>|<span data-ttu-id="3ac25-117">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-117">String</span></span>|
|<span data-ttu-id="3ac25-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3ac25-118">TABLE_SCHEM</span></span>|<span data-ttu-id="3ac25-119">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-119">String</span></span>|
|<span data-ttu-id="3ac25-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-120">TABLE_NAME</span></span>|<span data-ttu-id="3ac25-121">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-121">String</span></span>|
|<span data-ttu-id="3ac25-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-122">TABLE_TYPE</span></span>|<span data-ttu-id="3ac25-123">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-123">String</span></span>|
|<span data-ttu-id="3ac25-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-124">REMARKS</span></span>|<span data-ttu-id="3ac25-125">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="3ac25-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="3ac25-126">Indexes</span></span>

|<span data-ttu-id="3ac25-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-127">ColumnName</span></span>|<span data-ttu-id="3ac25-128">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="3ac25-129">TABLE_CAT</span></span>|<span data-ttu-id="3ac25-130">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-130">String</span></span>|
|<span data-ttu-id="3ac25-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3ac25-131">TABLE_SCHEM</span></span>|<span data-ttu-id="3ac25-132">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-132">String</span></span>|
|<span data-ttu-id="3ac25-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-133">TABLE_NAME</span></span>|<span data-ttu-id="3ac25-134">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-134">String</span></span>|
|<span data-ttu-id="3ac25-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="3ac25-135">NON_UNIQUE</span></span>|<span data-ttu-id="3ac25-136">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-136">Int16</span></span>|
|<span data-ttu-id="3ac25-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3ac25-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="3ac25-138">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-138">String</span></span>|
|<span data-ttu-id="3ac25-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-139">INDEX_NAME</span></span>|<span data-ttu-id="3ac25-140">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-140">String</span></span>|
|<span data-ttu-id="3ac25-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-141">TYPE</span></span>|<span data-ttu-id="3ac25-142">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-142">Int16</span></span>|
|<span data-ttu-id="3ac25-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3ac25-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="3ac25-144">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-144">Int16</span></span>|
|<span data-ttu-id="3ac25-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-145">COLUMN_NAME</span></span>|<span data-ttu-id="3ac25-146">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-146">String</span></span>|
|<span data-ttu-id="3ac25-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="3ac25-147">ASC_OR_DESC</span></span>|<span data-ttu-id="3ac25-148">String</span><span class="sxs-lookup"><span data-stu-id="3ac25-148">String</span></span>|
|<span data-ttu-id="3ac25-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="3ac25-149">CARDINALITY</span></span>|<span data-ttu-id="3ac25-150">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-150">Int32</span></span>|
|<span data-ttu-id="3ac25-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="3ac25-151">PAGES</span></span>|<span data-ttu-id="3ac25-152">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-152">Int32</span></span>|
|<span data-ttu-id="3ac25-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="3ac25-153">FILTER_CONDITION</span></span>|<span data-ttu-id="3ac25-154">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-154">String</span></span>|
|<span data-ttu-id="3ac25-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3ac25-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3ac25-156">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-156">String</span></span>|
|<span data-ttu-id="3ac25-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="3ac25-158">Byte</span><span class="sxs-lookup"><span data-stu-id="3ac25-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="3ac25-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="3ac25-159">Columns</span></span>

|<span data-ttu-id="3ac25-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-160">ColumnName</span></span>|<span data-ttu-id="3ac25-161">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="3ac25-162">TABLE_CAT</span></span>|<span data-ttu-id="3ac25-163">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-163">String</span></span>|
|<span data-ttu-id="3ac25-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3ac25-164">TABLE_SCHEM</span></span>|<span data-ttu-id="3ac25-165">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-165">String</span></span>|
|<span data-ttu-id="3ac25-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-166">TABLE_NAME</span></span>|<span data-ttu-id="3ac25-167">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-167">String</span></span>|
|<span data-ttu-id="3ac25-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-168">COLUMN_NAME</span></span>|<span data-ttu-id="3ac25-169">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-169">String</span></span>|
|<span data-ttu-id="3ac25-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-170">DATA_TYPE</span></span>|<span data-ttu-id="3ac25-171">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-171">Int16</span></span>|
|<span data-ttu-id="3ac25-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-172">TYPE_NAME</span></span>|<span data-ttu-id="3ac25-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-173">String</span></span>|
|<span data-ttu-id="3ac25-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3ac25-174">COLUMN_SIZE</span></span>|<span data-ttu-id="3ac25-175">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-175">Int32</span></span>|
|<span data-ttu-id="3ac25-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="3ac25-177">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-177">Int32</span></span>|
|<span data-ttu-id="3ac25-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3ac25-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3ac25-179">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-179">Int16</span></span>|
|<span data-ttu-id="3ac25-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3ac25-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3ac25-181">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-181">Int16</span></span>|
|<span data-ttu-id="3ac25-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-182">NULLABLE</span></span>|<span data-ttu-id="3ac25-183">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-183">Int16</span></span>|
|<span data-ttu-id="3ac25-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-184">REMARKS</span></span>|<span data-ttu-id="3ac25-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-185">String</span></span>|
|<span data-ttu-id="3ac25-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3ac25-186">COLUMN_DEF</span></span>|<span data-ttu-id="3ac25-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-187">String</span></span>|
|<span data-ttu-id="3ac25-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3ac25-189">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-189">Int16</span></span>|
|<span data-ttu-id="3ac25-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3ac25-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3ac25-191">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-191">Int16</span></span>|
|<span data-ttu-id="3ac25-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3ac25-193">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-193">Int32</span></span>|
|<span data-ttu-id="3ac25-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3ac25-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="3ac25-195">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-195">Int32</span></span>|
|<span data-ttu-id="3ac25-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-196">IS_NULLABLE</span></span>|<span data-ttu-id="3ac25-197">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-197">String</span></span>|
|<span data-ttu-id="3ac25-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3ac25-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="3ac25-199">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-199">String</span></span>|
|<span data-ttu-id="3ac25-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3ac25-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3ac25-201">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-201">String</span></span>|
|<span data-ttu-id="3ac25-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="3ac25-203">Byte</span><span class="sxs-lookup"><span data-stu-id="3ac25-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="3ac25-204">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3ac25-204">Procedures</span></span>

|<span data-ttu-id="3ac25-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-205">ColumnName</span></span>|<span data-ttu-id="3ac25-206">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3ac25-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="3ac25-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-208">String</span></span>|
|<span data-ttu-id="3ac25-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3ac25-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3ac25-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-210">String</span></span>|
|<span data-ttu-id="3ac25-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="3ac25-212">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-212">String</span></span>|
|<span data-ttu-id="3ac25-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3ac25-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="3ac25-214">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-214">Int32</span></span>|
|<span data-ttu-id="3ac25-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3ac25-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="3ac25-216">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-216">Int32</span></span>|
|<span data-ttu-id="3ac25-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="3ac25-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="3ac25-218">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-218">Int32</span></span>|
|<span data-ttu-id="3ac25-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-219">REMARKS</span></span>|<span data-ttu-id="3ac25-220">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-220">String</span></span>|
|<span data-ttu-id="3ac25-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3ac25-222">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="3ac25-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3ac25-223">ProcedureColumns</span></span>

|<span data-ttu-id="3ac25-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-224">ColumnName</span></span>|<span data-ttu-id="3ac25-225">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3ac25-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="3ac25-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-227">String</span></span>|
|<span data-ttu-id="3ac25-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3ac25-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3ac25-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-229">String</span></span>|
|<span data-ttu-id="3ac25-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="3ac25-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-231">String</span></span>|
|<span data-ttu-id="3ac25-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-232">COLUMN_NAME</span></span>|<span data-ttu-id="3ac25-233">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-233">String</span></span>|
|<span data-ttu-id="3ac25-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-234">COLUMN_TYPE</span></span>|<span data-ttu-id="3ac25-235">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-235">Int16</span></span>|
|<span data-ttu-id="3ac25-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-236">DATA_TYPE</span></span>|<span data-ttu-id="3ac25-237">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-237">Int16</span></span>|
|<span data-ttu-id="3ac25-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-238">TYPE_NAME</span></span>|<span data-ttu-id="3ac25-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-239">String</span></span>|
|<span data-ttu-id="3ac25-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3ac25-240">COLUMN_SIZE</span></span>|<span data-ttu-id="3ac25-241">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-241">Int32</span></span>|
|<span data-ttu-id="3ac25-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="3ac25-243">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-243">Int32</span></span>|
|<span data-ttu-id="3ac25-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3ac25-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3ac25-245">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-245">Int16</span></span>|
|<span data-ttu-id="3ac25-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3ac25-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3ac25-247">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-247">Int16</span></span>|
|<span data-ttu-id="3ac25-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-248">NULLABLE</span></span>|<span data-ttu-id="3ac25-249">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-249">Int16</span></span>|
|<span data-ttu-id="3ac25-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-250">REMARKS</span></span>|<span data-ttu-id="3ac25-251">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-251">String</span></span>|
|<span data-ttu-id="3ac25-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3ac25-252">COLUMN_DEF</span></span>|<span data-ttu-id="3ac25-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-253">String</span></span>|
|<span data-ttu-id="3ac25-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3ac25-255">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-255">Int16</span></span>|
|<span data-ttu-id="3ac25-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3ac25-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3ac25-257">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-257">Int16</span></span>|
|<span data-ttu-id="3ac25-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3ac25-259">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-259">Int32</span></span>|
|<span data-ttu-id="3ac25-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3ac25-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="3ac25-261">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-261">Int32</span></span>|
|<span data-ttu-id="3ac25-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-262">IS_NULLABLE</span></span>|<span data-ttu-id="3ac25-263">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-263">String</span></span>|
|<span data-ttu-id="3ac25-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3ac25-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="3ac25-265">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-265">String</span></span>|
|<span data-ttu-id="3ac25-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3ac25-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3ac25-267">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-267">String</span></span>|
|<span data-ttu-id="3ac25-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="3ac25-269">Byte</span><span class="sxs-lookup"><span data-stu-id="3ac25-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="3ac25-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3ac25-270">ProcedureParameters</span></span>

|<span data-ttu-id="3ac25-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-271">ColumnName</span></span>|<span data-ttu-id="3ac25-272">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3ac25-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="3ac25-274">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-274">String</span></span>|
|<span data-ttu-id="3ac25-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3ac25-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3ac25-276">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-276">String</span></span>|
|<span data-ttu-id="3ac25-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="3ac25-278">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-278">String</span></span>|
|<span data-ttu-id="3ac25-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-279">COLUMN_NAME</span></span>|<span data-ttu-id="3ac25-280">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-280">String</span></span>|
|<span data-ttu-id="3ac25-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-281">COLUMN_TYPE</span></span>|<span data-ttu-id="3ac25-282">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-282">Int16</span></span>|
|<span data-ttu-id="3ac25-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-283">DATA_TYPE</span></span>|<span data-ttu-id="3ac25-284">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-284">Int16</span></span>|
|<span data-ttu-id="3ac25-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-285">TYPE_NAME</span></span>|<span data-ttu-id="3ac25-286">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-286">String</span></span>|
|<span data-ttu-id="3ac25-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3ac25-287">COLUMN_SIZE</span></span>|<span data-ttu-id="3ac25-288">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-288">Int32</span></span>|
|<span data-ttu-id="3ac25-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="3ac25-290">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-290">Int32</span></span>|
|<span data-ttu-id="3ac25-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3ac25-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3ac25-292">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-292">Int16</span></span>|
|<span data-ttu-id="3ac25-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3ac25-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3ac25-294">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-294">Int16</span></span>|
|<span data-ttu-id="3ac25-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-295">NULLABLE</span></span>|<span data-ttu-id="3ac25-296">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-296">Int16</span></span>|
|<span data-ttu-id="3ac25-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-297">REMARKS</span></span>|<span data-ttu-id="3ac25-298">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-298">String</span></span>|
|<span data-ttu-id="3ac25-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3ac25-299">COLUMN_DEF</span></span>|<span data-ttu-id="3ac25-300">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-300">String</span></span>|
|<span data-ttu-id="3ac25-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3ac25-302">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-302">Int16</span></span>|
|<span data-ttu-id="3ac25-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3ac25-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3ac25-304">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-304">Int16</span></span>|
|<span data-ttu-id="3ac25-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3ac25-306">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-306">Int32</span></span>|
|<span data-ttu-id="3ac25-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3ac25-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="3ac25-308">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-308">Int32</span></span>|
|<span data-ttu-id="3ac25-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-309">IS_NULLABLE</span></span>|<span data-ttu-id="3ac25-310">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-310">String</span></span>|
|<span data-ttu-id="3ac25-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3ac25-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="3ac25-312">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-312">String</span></span>|
|<span data-ttu-id="3ac25-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3ac25-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3ac25-314">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-314">String</span></span>|
|<span data-ttu-id="3ac25-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="3ac25-316">Byte</span><span class="sxs-lookup"><span data-stu-id="3ac25-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="3ac25-317">Драйвер ODBC для Oracle (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3ac25-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="3ac25-318">Microsoft SQL Server драйвер ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="3ac25-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="3ac25-319">Таблицы</span><span class="sxs-lookup"><span data-stu-id="3ac25-319">Tables</span></span>

- <span data-ttu-id="3ac25-320">Столбцы</span><span class="sxs-lookup"><span data-stu-id="3ac25-320">Columns</span></span>

- <span data-ttu-id="3ac25-321">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3ac25-321">Procedures</span></span>

- <span data-ttu-id="3ac25-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3ac25-322">ProcedureColumns</span></span>

- <span data-ttu-id="3ac25-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3ac25-323">ProcedureParameters</span></span>

- <span data-ttu-id="3ac25-324">Представления</span><span class="sxs-lookup"><span data-stu-id="3ac25-324">Views</span></span>

- <span data-ttu-id="3ac25-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="3ac25-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="3ac25-326">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="3ac25-326">Tables and Views</span></span>

|<span data-ttu-id="3ac25-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-327">ColumnName</span></span>|<span data-ttu-id="3ac25-328">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3ac25-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3ac25-330">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-330">String</span></span>|
|<span data-ttu-id="3ac25-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ac25-331">TABLE_OWNER</span></span>|<span data-ttu-id="3ac25-332">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-332">String</span></span>|
|<span data-ttu-id="3ac25-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-333">TABLE_NAME</span></span>|<span data-ttu-id="3ac25-334">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-334">String</span></span>|
|<span data-ttu-id="3ac25-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-335">TABLE_TYPE</span></span>|<span data-ttu-id="3ac25-336">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-336">String</span></span>|
|<span data-ttu-id="3ac25-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-337">REMARKS</span></span>|<span data-ttu-id="3ac25-338">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="3ac25-339">Столбцы</span><span class="sxs-lookup"><span data-stu-id="3ac25-339">Columns</span></span>

|<span data-ttu-id="3ac25-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-340">ColumnName</span></span>|<span data-ttu-id="3ac25-341">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3ac25-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3ac25-343">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-343">String</span></span>|
|<span data-ttu-id="3ac25-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ac25-344">TABLE_OWNER</span></span>|<span data-ttu-id="3ac25-345">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-345">String</span></span>|
|<span data-ttu-id="3ac25-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-346">TABLE_NAME</span></span>|<span data-ttu-id="3ac25-347">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-347">String</span></span>|
|<span data-ttu-id="3ac25-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-348">COLUMN_NAME</span></span>|<span data-ttu-id="3ac25-349">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-349">String</span></span>|
|<span data-ttu-id="3ac25-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-350">DATA_TYPE</span></span>|<span data-ttu-id="3ac25-351">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-351">Int16</span></span>|
|<span data-ttu-id="3ac25-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-352">TYPE_NAME</span></span>|<span data-ttu-id="3ac25-353">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-353">String</span></span>|
|<span data-ttu-id="3ac25-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3ac25-354">PRECISION</span></span>|<span data-ttu-id="3ac25-355">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-355">Int32</span></span>|
|<span data-ttu-id="3ac25-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-356">LENGTH</span></span>|<span data-ttu-id="3ac25-357">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-357">Int32</span></span>|
|<span data-ttu-id="3ac25-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="3ac25-358">SCALE</span></span>|<span data-ttu-id="3ac25-359">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-359">Int16</span></span>|
|<span data-ttu-id="3ac25-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="3ac25-360">RADIX</span></span>|<span data-ttu-id="3ac25-361">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-361">Int16</span></span>|
|<span data-ttu-id="3ac25-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-362">NULLABLE</span></span>|<span data-ttu-id="3ac25-363">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-363">Int16</span></span>|
|<span data-ttu-id="3ac25-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-364">REMARKS</span></span>|<span data-ttu-id="3ac25-365">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-365">String</span></span>|
|<span data-ttu-id="3ac25-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3ac25-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="3ac25-367">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="3ac25-368">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3ac25-368">Procedures</span></span>

|<span data-ttu-id="3ac25-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-369">ColumnName</span></span>|<span data-ttu-id="3ac25-370">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3ac25-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3ac25-372">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-372">String</span></span>|
|<span data-ttu-id="3ac25-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ac25-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3ac25-374">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-374">String</span></span>|
|<span data-ttu-id="3ac25-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="3ac25-376">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-376">String</span></span>|
|<span data-ttu-id="3ac25-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3ac25-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="3ac25-378">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-378">Int16</span></span>|
|<span data-ttu-id="3ac25-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3ac25-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="3ac25-380">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-380">Int16</span></span>|
|<span data-ttu-id="3ac25-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="3ac25-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="3ac25-382">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-382">Int16</span></span>|
|<span data-ttu-id="3ac25-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-383">REMARKS</span></span>|<span data-ttu-id="3ac25-384">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-384">String</span></span>|
|<span data-ttu-id="3ac25-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3ac25-386">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="3ac25-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3ac25-387">ProcedureColumns</span></span>

|<span data-ttu-id="3ac25-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-388">ColumnName</span></span>|<span data-ttu-id="3ac25-389">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3ac25-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3ac25-391">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-391">String</span></span>|
|<span data-ttu-id="3ac25-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ac25-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3ac25-393">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-393">String</span></span>|
|<span data-ttu-id="3ac25-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="3ac25-395">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-395">String</span></span>|
|<span data-ttu-id="3ac25-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-396">COLUMN_NAME</span></span>|<span data-ttu-id="3ac25-397">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-397">String</span></span>|
|<span data-ttu-id="3ac25-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-398">COLUMN_TYPE</span></span>|<span data-ttu-id="3ac25-399">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-399">Int16</span></span>|
|<span data-ttu-id="3ac25-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-400">DATA_TYPE</span></span>|<span data-ttu-id="3ac25-401">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-401">Int16</span></span>|
|<span data-ttu-id="3ac25-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-402">TYPE_NAME</span></span>|<span data-ttu-id="3ac25-403">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-403">String</span></span>|
|<span data-ttu-id="3ac25-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3ac25-404">PRECISION</span></span>|<span data-ttu-id="3ac25-405">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-405">Int32</span></span>|
|<span data-ttu-id="3ac25-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-406">LENGTH</span></span>|<span data-ttu-id="3ac25-407">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-407">Int32</span></span>|
|<span data-ttu-id="3ac25-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="3ac25-408">SCALE</span></span>|<span data-ttu-id="3ac25-409">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-409">Int16</span></span>|
|<span data-ttu-id="3ac25-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="3ac25-410">RADIX</span></span>|<span data-ttu-id="3ac25-411">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-411">Int16</span></span>|
|<span data-ttu-id="3ac25-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-412">NULLABLE</span></span>|<span data-ttu-id="3ac25-413">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-413">Int16</span></span>|
|<span data-ttu-id="3ac25-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-414">REMARKS</span></span>|<span data-ttu-id="3ac25-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-415">String</span></span>|
|<span data-ttu-id="3ac25-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="3ac25-416">OVERLOAD</span></span>|<span data-ttu-id="3ac25-417">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-417">Int32</span></span>|
|<span data-ttu-id="3ac25-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3ac25-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="3ac25-419">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="3ac25-420">Драйвер ODBC для Jet (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3ac25-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="3ac25-421">Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="3ac25-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="3ac25-422">Таблицы</span><span class="sxs-lookup"><span data-stu-id="3ac25-422">Tables</span></span>

- <span data-ttu-id="3ac25-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="3ac25-423">Indexes</span></span>

- <span data-ttu-id="3ac25-424">Столбцы</span><span class="sxs-lookup"><span data-stu-id="3ac25-424">Columns</span></span>

- <span data-ttu-id="3ac25-425">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3ac25-425">Procedures</span></span>

- <span data-ttu-id="3ac25-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3ac25-426">ProcedureColumns</span></span>

- <span data-ttu-id="3ac25-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3ac25-427">ProcedureParameters</span></span>

- <span data-ttu-id="3ac25-428">Представления</span><span class="sxs-lookup"><span data-stu-id="3ac25-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="3ac25-429">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="3ac25-429">Tables and Views</span></span>

|<span data-ttu-id="3ac25-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-430">ColumnName</span></span>|<span data-ttu-id="3ac25-431">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3ac25-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3ac25-433">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-433">String</span></span>|
|<span data-ttu-id="3ac25-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ac25-434">TABLE_OWNER</span></span>|<span data-ttu-id="3ac25-435">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-435">String</span></span>|
|<span data-ttu-id="3ac25-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-436">TABLE_NAME</span></span>|<span data-ttu-id="3ac25-437">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-437">String</span></span>|
|<span data-ttu-id="3ac25-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-438">TABLE_TYPE</span></span>|<span data-ttu-id="3ac25-439">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-439">String</span></span>|
|<span data-ttu-id="3ac25-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-440">REMARKS</span></span>|<span data-ttu-id="3ac25-441">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="3ac25-442">Столбцы</span><span class="sxs-lookup"><span data-stu-id="3ac25-442">Columns</span></span>

|<span data-ttu-id="3ac25-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-443">ColumnName</span></span>|<span data-ttu-id="3ac25-444">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3ac25-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3ac25-446">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-446">String</span></span>|
|<span data-ttu-id="3ac25-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ac25-447">TABLE_OWNER</span></span>|<span data-ttu-id="3ac25-448">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-448">String</span></span>|
|<span data-ttu-id="3ac25-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-449">TABLE_NAME</span></span>|<span data-ttu-id="3ac25-450">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-450">String</span></span>|
|<span data-ttu-id="3ac25-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-451">COLUMN_NAME</span></span>|<span data-ttu-id="3ac25-452">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-452">String</span></span>|
|<span data-ttu-id="3ac25-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-453">DATA_TYPE</span></span>|<span data-ttu-id="3ac25-454">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-454">Int16</span></span>|
|<span data-ttu-id="3ac25-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-455">TYPE_NAME</span></span>|<span data-ttu-id="3ac25-456">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-456">String</span></span>|
|<span data-ttu-id="3ac25-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3ac25-457">PRECISION</span></span>|<span data-ttu-id="3ac25-458">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-458">Int32</span></span>|
|<span data-ttu-id="3ac25-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-459">LENGTH</span></span>|<span data-ttu-id="3ac25-460">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-460">Int32</span></span>|
|<span data-ttu-id="3ac25-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="3ac25-461">SCALE</span></span>|<span data-ttu-id="3ac25-462">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-462">Int16</span></span>|
|<span data-ttu-id="3ac25-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="3ac25-463">RADIX</span></span>|<span data-ttu-id="3ac25-464">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-464">Int16</span></span>|
|<span data-ttu-id="3ac25-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-465">NULLABLE</span></span>|<span data-ttu-id="3ac25-466">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-466">Int16</span></span>|
|<span data-ttu-id="3ac25-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-467">REMARKS</span></span>|<span data-ttu-id="3ac25-468">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-468">String</span></span>|
|<span data-ttu-id="3ac25-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3ac25-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="3ac25-470">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="3ac25-471">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3ac25-471">Procedures</span></span>

|<span data-ttu-id="3ac25-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-472">ColumnName</span></span>|<span data-ttu-id="3ac25-473">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3ac25-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3ac25-475">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-475">String</span></span>|
|<span data-ttu-id="3ac25-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ac25-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3ac25-477">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-477">String</span></span>|
|<span data-ttu-id="3ac25-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="3ac25-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-479">String</span></span>|
|<span data-ttu-id="3ac25-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3ac25-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="3ac25-481">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-481">Int16</span></span>|
|<span data-ttu-id="3ac25-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3ac25-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="3ac25-483">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-483">Int16</span></span>|
|<span data-ttu-id="3ac25-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="3ac25-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="3ac25-485">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-485">Int16</span></span>|
|<span data-ttu-id="3ac25-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-486">REMARKS</span></span>|<span data-ttu-id="3ac25-487">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-487">String</span></span>|
|<span data-ttu-id="3ac25-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3ac25-489">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="3ac25-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3ac25-490">ProcedureColumns</span></span>

|<span data-ttu-id="3ac25-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-491">ColumnName</span></span>|<span data-ttu-id="3ac25-492">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3ac25-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3ac25-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-494">String</span></span>|
|<span data-ttu-id="3ac25-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ac25-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3ac25-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-496">String</span></span>|
|<span data-ttu-id="3ac25-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="3ac25-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-498">String</span></span>|
|<span data-ttu-id="3ac25-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-499">COLUMN_NAME</span></span>|<span data-ttu-id="3ac25-500">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-500">String</span></span>|
|<span data-ttu-id="3ac25-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-501">COLUMN_TYPE</span></span>|<span data-ttu-id="3ac25-502">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-502">Int16</span></span>|
|<span data-ttu-id="3ac25-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-503">DATA_TYPE</span></span>|<span data-ttu-id="3ac25-504">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-504">Int16</span></span>|
|<span data-ttu-id="3ac25-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-505">TYPE_NAME</span></span>|<span data-ttu-id="3ac25-506">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-506">String</span></span>|
|<span data-ttu-id="3ac25-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3ac25-507">PRECISION</span></span>|<span data-ttu-id="3ac25-508">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-508">Int32</span></span>|
|<span data-ttu-id="3ac25-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-509">LENGTH</span></span>|<span data-ttu-id="3ac25-510">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-510">Int32</span></span>|
|<span data-ttu-id="3ac25-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="3ac25-511">SCALE</span></span>|<span data-ttu-id="3ac25-512">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-512">Int16</span></span>|
|<span data-ttu-id="3ac25-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="3ac25-513">RADIX</span></span>|<span data-ttu-id="3ac25-514">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-514">Int16</span></span>|
|<span data-ttu-id="3ac25-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-515">NULLABLE</span></span>|<span data-ttu-id="3ac25-516">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-516">Int16</span></span>|
|<span data-ttu-id="3ac25-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-517">REMARKS</span></span>|<span data-ttu-id="3ac25-518">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-518">String</span></span>|
|<span data-ttu-id="3ac25-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="3ac25-519">OVERLOAD</span></span>|<span data-ttu-id="3ac25-520">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-520">Int32</span></span>|
|<span data-ttu-id="3ac25-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3ac25-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="3ac25-522">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="3ac25-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3ac25-523">ProcedureParameters</span></span>

|<span data-ttu-id="3ac25-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3ac25-524">ColumnName</span></span>|<span data-ttu-id="3ac25-525">DataType</span><span class="sxs-lookup"><span data-stu-id="3ac25-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3ac25-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3ac25-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="3ac25-527">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-527">String</span></span>|
|<span data-ttu-id="3ac25-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3ac25-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3ac25-529">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-529">String</span></span>|
|<span data-ttu-id="3ac25-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="3ac25-531">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-531">String</span></span>|
|<span data-ttu-id="3ac25-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-532">COLUMN_NAME</span></span>|<span data-ttu-id="3ac25-533">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-533">String</span></span>|
|<span data-ttu-id="3ac25-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-534">COLUMN_TYPE</span></span>|<span data-ttu-id="3ac25-535">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-535">Int16</span></span>|
|<span data-ttu-id="3ac25-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-536">DATA_TYPE</span></span>|<span data-ttu-id="3ac25-537">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-537">Int16</span></span>|
|<span data-ttu-id="3ac25-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3ac25-538">TYPE_NAME</span></span>|<span data-ttu-id="3ac25-539">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-539">String</span></span>|
|<span data-ttu-id="3ac25-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3ac25-540">COLUMN_SIZE</span></span>|<span data-ttu-id="3ac25-541">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-541">Int32</span></span>|
|<span data-ttu-id="3ac25-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="3ac25-543">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-543">Int32</span></span>|
|<span data-ttu-id="3ac25-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3ac25-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3ac25-545">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-545">Int16</span></span>|
|<span data-ttu-id="3ac25-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3ac25-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3ac25-547">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-547">Int16</span></span>|
|<span data-ttu-id="3ac25-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-548">NULLABLE</span></span>|<span data-ttu-id="3ac25-549">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-549">Int16</span></span>|
|<span data-ttu-id="3ac25-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3ac25-550">REMARKS</span></span>|<span data-ttu-id="3ac25-551">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-551">String</span></span>|
|<span data-ttu-id="3ac25-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3ac25-552">COLUMN_DEF</span></span>|<span data-ttu-id="3ac25-553">Строковое</span><span class="sxs-lookup"><span data-stu-id="3ac25-553">String</span></span>|
|<span data-ttu-id="3ac25-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3ac25-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3ac25-555">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-555">Int16</span></span>|
|<span data-ttu-id="3ac25-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3ac25-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3ac25-557">Int16</span><span class="sxs-lookup"><span data-stu-id="3ac25-557">Int16</span></span>|
|<span data-ttu-id="3ac25-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3ac25-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3ac25-559">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-559">Int32</span></span>|
|<span data-ttu-id="3ac25-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3ac25-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="3ac25-561">Int32</span><span class="sxs-lookup"><span data-stu-id="3ac25-561">Int32</span></span>|
|<span data-ttu-id="3ac25-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3ac25-562">IS_NULLABLE</span></span>|<span data-ttu-id="3ac25-563">String</span><span class="sxs-lookup"><span data-stu-id="3ac25-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="3ac25-564">См. также</span><span class="sxs-lookup"><span data-stu-id="3ac25-564">See also</span></span>

- [<span data-ttu-id="3ac25-565">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3ac25-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
