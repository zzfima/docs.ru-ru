---
title: "Коллекции схемы ODBC"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b8c31f4e8b1463c184c9a8ff1cf64808783f030d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="49050-102">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="49050-102">ODBC Schema Collections</span></span>
<span data-ttu-id="49050-103">В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="49050-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="49050-104">Драйвер ODBC для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="49050-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="49050-105">Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем.</span><span class="sxs-lookup"><span data-stu-id="49050-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="49050-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="49050-106">Tables</span></span>  
  
-   <span data-ttu-id="49050-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="49050-107">Indexes</span></span>  
  
-   <span data-ttu-id="49050-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="49050-108">Columns</span></span>  
  
-   <span data-ttu-id="49050-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="49050-109">Procedures</span></span>  
  
-   <span data-ttu-id="49050-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="49050-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="49050-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="49050-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="49050-112">Представления</span><span class="sxs-lookup"><span data-stu-id="49050-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="49050-113">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="49050-113">Tables and Views</span></span>  
  
|<span data-ttu-id="49050-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-114">ColumnName</span></span>|<span data-ttu-id="49050-115">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="49050-116">TABLE_CAT</span></span>|<span data-ttu-id="49050-117">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-117">String</span></span>|  
|<span data-ttu-id="49050-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="49050-118">TABLE_SCHEM</span></span>|<span data-ttu-id="49050-119">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-119">String</span></span>|  
|<span data-ttu-id="49050-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-120">TABLE_NAME</span></span>|<span data-ttu-id="49050-121">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-121">String</span></span>|  
|<span data-ttu-id="49050-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-122">TABLE_TYPE</span></span>|<span data-ttu-id="49050-123">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-123">String</span></span>|  
|<span data-ttu-id="49050-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-124">REMARKS</span></span>|<span data-ttu-id="49050-125">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="49050-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="49050-126">Indexes</span></span>  
  
|<span data-ttu-id="49050-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-127">ColumnName</span></span>|<span data-ttu-id="49050-128">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="49050-129">TABLE_CAT</span></span>|<span data-ttu-id="49050-130">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-130">String</span></span>|  
|<span data-ttu-id="49050-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="49050-131">TABLE_SCHEM</span></span>|<span data-ttu-id="49050-132">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-132">String</span></span>|  
|<span data-ttu-id="49050-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-133">TABLE_NAME</span></span>|<span data-ttu-id="49050-134">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-134">String</span></span>|  
|<span data-ttu-id="49050-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="49050-135">NON_UNIQUE</span></span>|<span data-ttu-id="49050-136">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-136">Int16</span></span>|  
|<span data-ttu-id="49050-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="49050-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="49050-138">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-138">String</span></span>|  
|<span data-ttu-id="49050-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-139">INDEX_NAME</span></span>|<span data-ttu-id="49050-140">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-140">String</span></span>|  
|<span data-ttu-id="49050-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-141">TYPE</span></span>|<span data-ttu-id="49050-142">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-142">Int16</span></span>|  
|<span data-ttu-id="49050-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="49050-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="49050-144">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-144">Int16</span></span>|  
|<span data-ttu-id="49050-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-145">COLUMN_NAME</span></span>|<span data-ttu-id="49050-146">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-146">String</span></span>|  
|<span data-ttu-id="49050-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="49050-147">ASC_OR_DESC</span></span>|<span data-ttu-id="49050-148">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-148">String</span></span>|  
|<span data-ttu-id="49050-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="49050-149">CARDINATLITY</span></span>|<span data-ttu-id="49050-150">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-150">Int32</span></span>|  
|<span data-ttu-id="49050-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="49050-151">PAGES</span></span>|<span data-ttu-id="49050-152">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-152">Int32</span></span>|  
|<span data-ttu-id="49050-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="49050-153">FILTER_CONDITION</span></span>|<span data-ttu-id="49050-154">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-154">String</span></span>|  
|<span data-ttu-id="49050-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="49050-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="49050-156">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-156">String</span></span>|  
|<span data-ttu-id="49050-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="49050-158">Byte</span><span class="sxs-lookup"><span data-stu-id="49050-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="49050-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="49050-159">Columns</span></span>  
  
|<span data-ttu-id="49050-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-160">ColumnName</span></span>|<span data-ttu-id="49050-161">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="49050-162">TABLE_CAT</span></span>|<span data-ttu-id="49050-163">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-163">String</span></span>|  
|<span data-ttu-id="49050-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="49050-164">TABLE_SCHEM</span></span>|<span data-ttu-id="49050-165">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-165">String</span></span>|  
|<span data-ttu-id="49050-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-166">TABLE_NAME</span></span>|<span data-ttu-id="49050-167">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-167">String</span></span>|  
|<span data-ttu-id="49050-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-168">COLUMN_NAME</span></span>|<span data-ttu-id="49050-169">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-169">String</span></span>|  
|<span data-ttu-id="49050-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-170">DATA_TYPE</span></span>|<span data-ttu-id="49050-171">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-171">Int16</span></span>|  
|<span data-ttu-id="49050-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-172">TYPE_NAME</span></span>|<span data-ttu-id="49050-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-173">String</span></span>|  
|<span data-ttu-id="49050-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="49050-174">COLUMN_SIZE</span></span>|<span data-ttu-id="49050-175">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-175">Int32</span></span>|  
|<span data-ttu-id="49050-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="49050-177">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-177">Int32</span></span>|  
|<span data-ttu-id="49050-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="49050-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="49050-179">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-179">Int16</span></span>|  
|<span data-ttu-id="49050-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="49050-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="49050-181">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-181">Int16</span></span>|  
|<span data-ttu-id="49050-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-182">NULLABLE</span></span>|<span data-ttu-id="49050-183">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-183">Int16</span></span>|  
|<span data-ttu-id="49050-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-184">REMARKS</span></span>|<span data-ttu-id="49050-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-185">String</span></span>|  
|<span data-ttu-id="49050-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="49050-186">COLUMN_DEF</span></span>|<span data-ttu-id="49050-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-187">String</span></span>|  
|<span data-ttu-id="49050-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="49050-189">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-189">Int16</span></span>|  
|<span data-ttu-id="49050-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="49050-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="49050-191">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-191">Int16</span></span>|  
|<span data-ttu-id="49050-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="49050-193">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-193">Int32</span></span>|  
|<span data-ttu-id="49050-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="49050-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="49050-195">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-195">Int32</span></span>|  
|<span data-ttu-id="49050-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-196">IS_NULLABLE</span></span>|<span data-ttu-id="49050-197">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-197">String</span></span>|  
|<span data-ttu-id="49050-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="49050-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="49050-199">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-199">String</span></span>|  
|<span data-ttu-id="49050-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="49050-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="49050-201">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-201">String</span></span>|  
|<span data-ttu-id="49050-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="49050-203">Byte</span><span class="sxs-lookup"><span data-stu-id="49050-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="49050-204">Процедуры</span><span class="sxs-lookup"><span data-stu-id="49050-204">Procedures</span></span>  
  
|<span data-ttu-id="49050-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-205">ColumnName</span></span>|<span data-ttu-id="49050-206">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="49050-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="49050-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-208">String</span></span>|  
|<span data-ttu-id="49050-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="49050-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="49050-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-210">String</span></span>|  
|<span data-ttu-id="49050-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="49050-212">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-212">String</span></span>|  
|<span data-ttu-id="49050-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="49050-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="49050-214">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-214">Int32</span></span>|  
|<span data-ttu-id="49050-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="49050-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="49050-216">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-216">Int32</span></span>|  
|<span data-ttu-id="49050-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="49050-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="49050-218">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-218">Int32</span></span>|  
|<span data-ttu-id="49050-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-219">REMARKS</span></span>|<span data-ttu-id="49050-220">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-220">String</span></span>|  
|<span data-ttu-id="49050-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="49050-222">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="49050-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="49050-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="49050-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-224">ColumnName</span></span>|<span data-ttu-id="49050-225">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="49050-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="49050-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-227">String</span></span>|  
|<span data-ttu-id="49050-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="49050-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="49050-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-229">String</span></span>|  
|<span data-ttu-id="49050-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="49050-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-231">String</span></span>|  
|<span data-ttu-id="49050-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-232">COLUMN_NAME</span></span>|<span data-ttu-id="49050-233">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-233">String</span></span>|  
|<span data-ttu-id="49050-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-234">COLUMN_TYPE</span></span>|<span data-ttu-id="49050-235">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-235">Int16</span></span>|  
|<span data-ttu-id="49050-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-236">DATA_TYPE</span></span>|<span data-ttu-id="49050-237">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-237">Int16</span></span>|  
|<span data-ttu-id="49050-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-238">TYPE_NAME</span></span>|<span data-ttu-id="49050-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-239">String</span></span>|  
|<span data-ttu-id="49050-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="49050-240">COLUMN_SIZE</span></span>|<span data-ttu-id="49050-241">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-241">Int32</span></span>|  
|<span data-ttu-id="49050-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="49050-243">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-243">Int32</span></span>|  
|<span data-ttu-id="49050-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="49050-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="49050-245">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-245">Int16</span></span>|  
|<span data-ttu-id="49050-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="49050-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="49050-247">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-247">Int16</span></span>|  
|<span data-ttu-id="49050-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-248">NULLABLE</span></span>|<span data-ttu-id="49050-249">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-249">Int16</span></span>|  
|<span data-ttu-id="49050-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-250">REMARKS</span></span>|<span data-ttu-id="49050-251">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-251">String</span></span>|  
|<span data-ttu-id="49050-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="49050-252">COLUMN_DEF</span></span>|<span data-ttu-id="49050-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-253">String</span></span>|  
|<span data-ttu-id="49050-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="49050-255">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-255">Int16</span></span>|  
|<span data-ttu-id="49050-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="49050-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="49050-257">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-257">Int16</span></span>|  
|<span data-ttu-id="49050-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="49050-259">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-259">Int32</span></span>|  
|<span data-ttu-id="49050-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="49050-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="49050-261">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-261">Int32</span></span>|  
|<span data-ttu-id="49050-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-262">IS_NULLABLE</span></span>|<span data-ttu-id="49050-263">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-263">String</span></span>|  
|<span data-ttu-id="49050-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="49050-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="49050-265">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-265">String</span></span>|  
|<span data-ttu-id="49050-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="49050-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="49050-267">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-267">String</span></span>|  
|<span data-ttu-id="49050-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="49050-269">Byte</span><span class="sxs-lookup"><span data-stu-id="49050-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="49050-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="49050-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="49050-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-271">ColumnName</span></span>|<span data-ttu-id="49050-272">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="49050-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="49050-274">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-274">String</span></span>|  
|<span data-ttu-id="49050-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="49050-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="49050-276">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-276">String</span></span>|  
|<span data-ttu-id="49050-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="49050-278">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-278">String</span></span>|  
|<span data-ttu-id="49050-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-279">COLUMN_NAME</span></span>|<span data-ttu-id="49050-280">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-280">String</span></span>|  
|<span data-ttu-id="49050-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-281">COLUMN_TYPE</span></span>|<span data-ttu-id="49050-282">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-282">Int16</span></span>|  
|<span data-ttu-id="49050-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-283">DATA_TYPE</span></span>|<span data-ttu-id="49050-284">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-284">Int16</span></span>|  
|<span data-ttu-id="49050-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-285">TYPE_NAME</span></span>|<span data-ttu-id="49050-286">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-286">String</span></span>|  
|<span data-ttu-id="49050-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="49050-287">COLUMN_SIZE</span></span>|<span data-ttu-id="49050-288">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-288">Int32</span></span>|  
|<span data-ttu-id="49050-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="49050-290">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-290">Int32</span></span>|  
|<span data-ttu-id="49050-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="49050-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="49050-292">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-292">Int16</span></span>|  
|<span data-ttu-id="49050-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="49050-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="49050-294">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-294">Int16</span></span>|  
|<span data-ttu-id="49050-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-295">NULLABLE</span></span>|<span data-ttu-id="49050-296">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-296">Int16</span></span>|  
|<span data-ttu-id="49050-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-297">REMARKS</span></span>|<span data-ttu-id="49050-298">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-298">String</span></span>|  
|<span data-ttu-id="49050-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="49050-299">COLUMN_DEF</span></span>|<span data-ttu-id="49050-300">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-300">String</span></span>|  
|<span data-ttu-id="49050-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="49050-302">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-302">Int16</span></span>|  
|<span data-ttu-id="49050-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="49050-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="49050-304">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-304">Int16</span></span>|  
|<span data-ttu-id="49050-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="49050-306">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-306">Int32</span></span>|  
|<span data-ttu-id="49050-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="49050-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="49050-308">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-308">Int32</span></span>|  
|<span data-ttu-id="49050-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-309">IS_NULLABLE</span></span>|<span data-ttu-id="49050-310">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-310">String</span></span>|  
|<span data-ttu-id="49050-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="49050-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="49050-312">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-312">String</span></span>|  
|<span data-ttu-id="49050-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="49050-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="49050-314">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-314">String</span></span>|  
|<span data-ttu-id="49050-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="49050-316">Byte</span><span class="sxs-lookup"><span data-stu-id="49050-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="49050-317">Драйвер ODBC для Oracle (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="49050-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="49050-318">Microsoft SQL Server драйвер ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем.</span><span class="sxs-lookup"><span data-stu-id="49050-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="49050-319">Таблицы</span><span class="sxs-lookup"><span data-stu-id="49050-319">Tables</span></span>  
  
-   <span data-ttu-id="49050-320">Столбцы</span><span class="sxs-lookup"><span data-stu-id="49050-320">Columns</span></span>  
  
-   <span data-ttu-id="49050-321">Процедуры</span><span class="sxs-lookup"><span data-stu-id="49050-321">Procedures</span></span>  
  
-   <span data-ttu-id="49050-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="49050-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="49050-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="49050-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="49050-324">Представления</span><span class="sxs-lookup"><span data-stu-id="49050-324">Views</span></span>  
  
-   <span data-ttu-id="49050-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="49050-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="49050-326">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="49050-326">Tables and Views</span></span>  
  
|<span data-ttu-id="49050-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-327">ColumnName</span></span>|<span data-ttu-id="49050-328">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="49050-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="49050-330">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-330">String</span></span>|  
|<span data-ttu-id="49050-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="49050-331">TABLE_OWNER</span></span>|<span data-ttu-id="49050-332">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-332">String</span></span>|  
|<span data-ttu-id="49050-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-333">TABLE_NAME</span></span>|<span data-ttu-id="49050-334">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-334">String</span></span>|  
|<span data-ttu-id="49050-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-335">TABLE_TYPE</span></span>|<span data-ttu-id="49050-336">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-336">String</span></span>|  
|<span data-ttu-id="49050-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-337">REMARKS</span></span>|<span data-ttu-id="49050-338">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="49050-339">Столбцы</span><span class="sxs-lookup"><span data-stu-id="49050-339">Columns</span></span>  
  
|<span data-ttu-id="49050-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-340">ColumnName</span></span>|<span data-ttu-id="49050-341">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="49050-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="49050-343">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-343">String</span></span>|  
|<span data-ttu-id="49050-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="49050-344">TABLE_OWNER</span></span>|<span data-ttu-id="49050-345">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-345">String</span></span>|  
|<span data-ttu-id="49050-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-346">TABLE_NAME</span></span>|<span data-ttu-id="49050-347">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-347">String</span></span>|  
|<span data-ttu-id="49050-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-348">COLUMN_NAME</span></span>|<span data-ttu-id="49050-349">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-349">String</span></span>|  
|<span data-ttu-id="49050-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-350">DATA_TYPE</span></span>|<span data-ttu-id="49050-351">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-351">Int16</span></span>|  
|<span data-ttu-id="49050-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-352">TYPE_NAME</span></span>|<span data-ttu-id="49050-353">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-353">String</span></span>|  
|<span data-ttu-id="49050-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="49050-354">PRECISION</span></span>|<span data-ttu-id="49050-355">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-355">Int32</span></span>|  
|<span data-ttu-id="49050-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-356">LENGTH</span></span>|<span data-ttu-id="49050-357">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-357">Int32</span></span>|  
|<span data-ttu-id="49050-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="49050-358">SCALE</span></span>|<span data-ttu-id="49050-359">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-359">Int16</span></span>|  
|<span data-ttu-id="49050-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="49050-360">RADIX</span></span>|<span data-ttu-id="49050-361">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-361">Int16</span></span>|  
|<span data-ttu-id="49050-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-362">NULLABLE</span></span>|<span data-ttu-id="49050-363">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-363">Int16</span></span>|  
|<span data-ttu-id="49050-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-364">REMARKS</span></span>|<span data-ttu-id="49050-365">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-365">String</span></span>|  
|<span data-ttu-id="49050-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="49050-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="49050-367">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="49050-368">Процедуры</span><span class="sxs-lookup"><span data-stu-id="49050-368">Procedures</span></span>  
  
|<span data-ttu-id="49050-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-369">ColumnName</span></span>|<span data-ttu-id="49050-370">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="49050-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="49050-372">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-372">String</span></span>|  
|<span data-ttu-id="49050-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="49050-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="49050-374">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-374">String</span></span>|  
|<span data-ttu-id="49050-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="49050-376">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-376">String</span></span>|  
|<span data-ttu-id="49050-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="49050-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="49050-378">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-378">Int16</span></span>|  
|<span data-ttu-id="49050-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="49050-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="49050-380">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-380">Int16</span></span>|  
|<span data-ttu-id="49050-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="49050-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="49050-382">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-382">Int16</span></span>|  
|<span data-ttu-id="49050-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-383">REMARKS</span></span>|<span data-ttu-id="49050-384">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-384">String</span></span>|  
|<span data-ttu-id="49050-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="49050-386">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="49050-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="49050-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="49050-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-388">ColumnName</span></span>|<span data-ttu-id="49050-389">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="49050-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="49050-391">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-391">String</span></span>|  
|<span data-ttu-id="49050-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="49050-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="49050-393">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-393">String</span></span>|  
|<span data-ttu-id="49050-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="49050-395">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-395">String</span></span>|  
|<span data-ttu-id="49050-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-396">COLUMN_NAME</span></span>|<span data-ttu-id="49050-397">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-397">String</span></span>|  
|<span data-ttu-id="49050-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-398">COLUMN_TYPE</span></span>|<span data-ttu-id="49050-399">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-399">Int16</span></span>|  
|<span data-ttu-id="49050-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-400">DATA_TYPE</span></span>|<span data-ttu-id="49050-401">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-401">Int16</span></span>|  
|<span data-ttu-id="49050-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-402">TYPE_NAME</span></span>|<span data-ttu-id="49050-403">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-403">String</span></span>|  
|<span data-ttu-id="49050-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="49050-404">PRECISION</span></span>|<span data-ttu-id="49050-405">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-405">Int32</span></span>|  
|<span data-ttu-id="49050-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-406">LENGTH</span></span>|<span data-ttu-id="49050-407">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-407">Int32</span></span>|  
|<span data-ttu-id="49050-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="49050-408">SCALE</span></span>|<span data-ttu-id="49050-409">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-409">Int16</span></span>|  
|<span data-ttu-id="49050-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="49050-410">RADIX</span></span>|<span data-ttu-id="49050-411">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-411">Int16</span></span>|  
|<span data-ttu-id="49050-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-412">NULLABLE</span></span>|<span data-ttu-id="49050-413">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-413">Int16</span></span>|  
|<span data-ttu-id="49050-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-414">REMARKS</span></span>|<span data-ttu-id="49050-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-415">String</span></span>|  
|<span data-ttu-id="49050-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="49050-416">OVERLOAD</span></span>|<span data-ttu-id="49050-417">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-417">Int32</span></span>|  
|<span data-ttu-id="49050-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="49050-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="49050-419">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="49050-420">Драйвер ODBC для Jet (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="49050-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="49050-421">Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="49050-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="49050-422">Таблицы</span><span class="sxs-lookup"><span data-stu-id="49050-422">Tables</span></span>  
  
-   <span data-ttu-id="49050-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="49050-423">Indexes</span></span>  
  
-   <span data-ttu-id="49050-424">Столбцы</span><span class="sxs-lookup"><span data-stu-id="49050-424">Columns</span></span>  
  
-   <span data-ttu-id="49050-425">Процедуры</span><span class="sxs-lookup"><span data-stu-id="49050-425">Procedures</span></span>  
  
-   <span data-ttu-id="49050-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="49050-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="49050-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="49050-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="49050-428">Представления</span><span class="sxs-lookup"><span data-stu-id="49050-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="49050-429">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="49050-429">Tables and Views</span></span>  
  
|<span data-ttu-id="49050-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-430">ColumnName</span></span>|<span data-ttu-id="49050-431">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="49050-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="49050-433">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-433">String</span></span>|  
|<span data-ttu-id="49050-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="49050-434">TABLE_OWNER</span></span>|<span data-ttu-id="49050-435">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-435">String</span></span>|  
|<span data-ttu-id="49050-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-436">TABLE_NAME</span></span>|<span data-ttu-id="49050-437">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-437">String</span></span>|  
|<span data-ttu-id="49050-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-438">TABLE_TYPE</span></span>|<span data-ttu-id="49050-439">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-439">String</span></span>|  
|<span data-ttu-id="49050-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-440">REMARKS</span></span>|<span data-ttu-id="49050-441">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="49050-442">Столбцы</span><span class="sxs-lookup"><span data-stu-id="49050-442">Columns</span></span>  
  
|<span data-ttu-id="49050-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-443">ColumnName</span></span>|<span data-ttu-id="49050-444">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="49050-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="49050-446">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-446">String</span></span>|  
|<span data-ttu-id="49050-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="49050-447">TABLE_OWNER</span></span>|<span data-ttu-id="49050-448">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-448">String</span></span>|  
|<span data-ttu-id="49050-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-449">TABLE_NAME</span></span>|<span data-ttu-id="49050-450">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-450">String</span></span>|  
|<span data-ttu-id="49050-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-451">COLUMN_NAME</span></span>|<span data-ttu-id="49050-452">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-452">String</span></span>|  
|<span data-ttu-id="49050-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-453">DATA_TYPE</span></span>|<span data-ttu-id="49050-454">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-454">Int16</span></span>|  
|<span data-ttu-id="49050-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-455">TYPE_NAME</span></span>|<span data-ttu-id="49050-456">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-456">String</span></span>|  
|<span data-ttu-id="49050-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="49050-457">PRECISION</span></span>|<span data-ttu-id="49050-458">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-458">Int32</span></span>|  
|<span data-ttu-id="49050-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-459">LENGTH</span></span>|<span data-ttu-id="49050-460">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-460">Int32</span></span>|  
|<span data-ttu-id="49050-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="49050-461">SCALE</span></span>|<span data-ttu-id="49050-462">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-462">Int16</span></span>|  
|<span data-ttu-id="49050-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="49050-463">RADIX</span></span>|<span data-ttu-id="49050-464">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-464">Int16</span></span>|  
|<span data-ttu-id="49050-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-465">NULLABLE</span></span>|<span data-ttu-id="49050-466">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-466">Int16</span></span>|  
|<span data-ttu-id="49050-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-467">REMARKS</span></span>|<span data-ttu-id="49050-468">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-468">String</span></span>|  
|<span data-ttu-id="49050-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="49050-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="49050-470">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="49050-471">Процедуры</span><span class="sxs-lookup"><span data-stu-id="49050-471">Procedures</span></span>  
  
|<span data-ttu-id="49050-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-472">ColumnName</span></span>|<span data-ttu-id="49050-473">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="49050-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="49050-475">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-475">String</span></span>|  
|<span data-ttu-id="49050-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="49050-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="49050-477">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-477">String</span></span>|  
|<span data-ttu-id="49050-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="49050-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-479">String</span></span>|  
|<span data-ttu-id="49050-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="49050-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="49050-481">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-481">Int16</span></span>|  
|<span data-ttu-id="49050-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="49050-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="49050-483">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-483">Int16</span></span>|  
|<span data-ttu-id="49050-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="49050-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="49050-485">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-485">Int16</span></span>|  
|<span data-ttu-id="49050-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-486">REMARKS</span></span>|<span data-ttu-id="49050-487">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-487">String</span></span>|  
|<span data-ttu-id="49050-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="49050-489">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="49050-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="49050-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="49050-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-491">ColumnName</span></span>|<span data-ttu-id="49050-492">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="49050-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="49050-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-494">String</span></span>|  
|<span data-ttu-id="49050-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="49050-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="49050-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-496">String</span></span>|  
|<span data-ttu-id="49050-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="49050-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-498">String</span></span>|  
|<span data-ttu-id="49050-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-499">COLUMN_NAME</span></span>|<span data-ttu-id="49050-500">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-500">String</span></span>|  
|<span data-ttu-id="49050-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-501">COLUMN_TYPE</span></span>|<span data-ttu-id="49050-502">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-502">Int16</span></span>|  
|<span data-ttu-id="49050-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-503">DATA_TYPE</span></span>|<span data-ttu-id="49050-504">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-504">Int16</span></span>|  
|<span data-ttu-id="49050-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-505">TYPE_NAME</span></span>|<span data-ttu-id="49050-506">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-506">String</span></span>|  
|<span data-ttu-id="49050-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="49050-507">PRECISION</span></span>|<span data-ttu-id="49050-508">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-508">Int32</span></span>|  
|<span data-ttu-id="49050-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-509">LENGTH</span></span>|<span data-ttu-id="49050-510">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-510">Int32</span></span>|  
|<span data-ttu-id="49050-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="49050-511">SCALE</span></span>|<span data-ttu-id="49050-512">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-512">Int16</span></span>|  
|<span data-ttu-id="49050-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="49050-513">RADIX</span></span>|<span data-ttu-id="49050-514">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-514">Int16</span></span>|  
|<span data-ttu-id="49050-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-515">NULLABLE</span></span>|<span data-ttu-id="49050-516">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-516">Int16</span></span>|  
|<span data-ttu-id="49050-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-517">REMARKS</span></span>|<span data-ttu-id="49050-518">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-518">String</span></span>|  
|<span data-ttu-id="49050-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="49050-519">OVERLOAD</span></span>|<span data-ttu-id="49050-520">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-520">Int32</span></span>|  
|<span data-ttu-id="49050-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="49050-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="49050-522">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="49050-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="49050-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="49050-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="49050-524">ColumnName</span></span>|<span data-ttu-id="49050-525">DataType</span><span class="sxs-lookup"><span data-stu-id="49050-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="49050-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="49050-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="49050-527">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-527">String</span></span>|  
|<span data-ttu-id="49050-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="49050-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="49050-529">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-529">String</span></span>|  
|<span data-ttu-id="49050-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="49050-531">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-531">String</span></span>|  
|<span data-ttu-id="49050-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-532">COLUMN_NAME</span></span>|<span data-ttu-id="49050-533">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-533">String</span></span>|  
|<span data-ttu-id="49050-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-534">COLUMN_TYPE</span></span>|<span data-ttu-id="49050-535">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-535">Int16</span></span>|  
|<span data-ttu-id="49050-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-536">DATA_TYPE</span></span>|<span data-ttu-id="49050-537">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-537">Int16</span></span>|  
|<span data-ttu-id="49050-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="49050-538">TYPE_NAME</span></span>|<span data-ttu-id="49050-539">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-539">String</span></span>|  
|<span data-ttu-id="49050-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="49050-540">COLUMN_SIZE</span></span>|<span data-ttu-id="49050-541">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-541">Int32</span></span>|  
|<span data-ttu-id="49050-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="49050-543">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-543">Int32</span></span>|  
|<span data-ttu-id="49050-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="49050-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="49050-545">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-545">Int16</span></span>|  
|<span data-ttu-id="49050-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="49050-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="49050-547">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-547">Int16</span></span>|  
|<span data-ttu-id="49050-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-548">NULLABLE</span></span>|<span data-ttu-id="49050-549">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-549">Int16</span></span>|  
|<span data-ttu-id="49050-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="49050-550">REMARKS</span></span>|<span data-ttu-id="49050-551">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-551">String</span></span>|  
|<span data-ttu-id="49050-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="49050-552">COLUMN_DEF</span></span>|<span data-ttu-id="49050-553">Строковое</span><span class="sxs-lookup"><span data-stu-id="49050-553">String</span></span>|  
|<span data-ttu-id="49050-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="49050-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="49050-555">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-555">Int16</span></span>|  
|<span data-ttu-id="49050-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="49050-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="49050-557">Int16</span><span class="sxs-lookup"><span data-stu-id="49050-557">Int16</span></span>|  
|<span data-ttu-id="49050-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="49050-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="49050-559">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-559">Int32</span></span>|  
|<span data-ttu-id="49050-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="49050-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="49050-561">Int32</span><span class="sxs-lookup"><span data-stu-id="49050-561">Int32</span></span>|  
|<span data-ttu-id="49050-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="49050-562">IS_NULLABLE</span></span>|<span data-ttu-id="49050-563">String</span><span class="sxs-lookup"><span data-stu-id="49050-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49050-564">См. также</span><span class="sxs-lookup"><span data-stu-id="49050-564">See Also</span></span>  
 [<span data-ttu-id="49050-565">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="49050-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
