# 📦 Best Practices Guide - Inventory System

## 🎯 Objective

This document will help you maintain an organized, consistent, and easy-to-query inventory using the Telegram bot.

---

## ✅ Required Fields

Each item MUST have these 3 fields:

1. **Code** - Unique item identifier
2. **Name** - Item description
3. **Quantity** - Number of units

The other fields (Category, Condition, Donor, Date Received, Location, Notes) are optional but highly recommended.

---

## 📝 Best Practices by Field

### 1. CODE

**✅ Correct:**
- `CHAIR-001`, `TABLE-045`, `COMP-023`
- `LAP-2024-001`, `DON-MARY-15`

**❌ Avoid:**
- `chair1` (use uppercase)
- `Table 01` (avoid spaces, use hyphens)
- Duplicate codes

**Rules:**
- Always in UPPERCASE
- Use format: `CATEGORY-NUMBER` or `CATEGORY-YEAR-NUMBER`
- No spaces (use hyphens `-`)
- Each code must be unique
- **Suggestion:** Define prefixes for each category (e.g., CHAIR, TABLE, COMP for computers)

---

### 2. NAME

**✅ Correct:**
- `Ergonomic office chair`
- `Rectangular conference table`
- `HP Pavilion 15" laptop`

**❌ Avoid:**
- `chair` (too vague)
- `OFFICE CHAIR` (don't use all caps)
- `offise chiar` (spelling errors)

**Rules:**
- First letter capitalized, rest lowercase
- Be specific and descriptive
- Include brand/model if relevant
- Avoid confusing abbreviations
- Use proper spelling

---

### 3. CATEGORY

**✅ Correct:**
- `Furniture`, `Electronics`, `Stationery`
- `Tools`, `Medical equipment`, `Books`

**❌ Avoid:**
- `furniture` (without initial capital)
- `Furn` (abbreviations)
- Using different names for the same thing: `Furniture` and `Office furniture`

**Rules:**
- Define a fixed catalog of categories
- First letter capitalized
- Be consistent (always use the same name)
- Maintain a list of valid categories

**Suggested Categories:**
- Furniture
- Electronics
- Computers
- Tools
- Stationery
- Medical supplies
- Sports
- Books
- Kitchen
- Cleaning

---

### 4. QUANTITY

**✅ Correct:**
- `1`, `5`, `25`, `100`

**❌ Avoid:**
- `five` (use numbers)
- `5 units` (only the number)
- Leaving it empty

**Rules:**
- Always use numbers
- No units of measurement in this field (e.g., don't put "5 kg")
- This field is REQUIRED

---

### 5. CONDITION

**✅ Correct (use only these options):**
- `New`
- `Excellent`
- `Good`
- `Fair`
- `Poor`
- `Needs repair`

**❌ Avoid:**
- `more or less` (use standard options)
- `good` (without initial capital)
- Inventing new states

**Rules:**
- Use ONLY the options listed above
- First letter capitalized
- Be objective in evaluation

---

### 6. DONOR

**✅ Correct:**
- `Maria Gonzalez`
- `XYZ Company Inc.`
- `Help Foundation`
- `Anonymous` (if unknown)

**❌ Avoid:**
- `maria` (without capitals in proper names)
- `M.` (abbreviations)

**Rules:**
- Proper names with initial capital
- Use full name when possible
- If not applicable, leave empty or put "N/A"

---

### 7. DATE RECEIVED

**✅ Correct:**
- `15/01/2025`
- `03/12/2024`

**❌ Avoid:**
- `15-01-2025` (use `/` not `-`)
- `January 15` (use DD/MM/YYYY format)
- `2025-01-15` (not ISO format)

**Rules:**
- REQUIRED format: **DD/MM/YYYY**
- Always with 2 digits for day and month
- 4 digits for year
- Use `/` as separator

---

### 8. LOCATION

**✅ Correct:**
- `Warehouse A - Shelf 3`
- `Main office - Desk 5`
- `Storage 2 - North section`

**❌ Avoid:**
- `warehouse` (be more specific)
- `over there` (vague)
- Inconsistent locations

**Rules:**
- Be specific
- Use format: `Main area - Specific detail`
- Keep area names consistent
- Helps find items quickly

**Suggested Locations (adapt to your space):**
- Warehouse A, Warehouse B, Warehouse C
- Office 1, Office 2
- General storage
- Meeting room
- Reception
- Maintenance area

---

### 9. NOTES

**✅ Correct:**
- `Requires additional power cable`
- `Donated by 2024 Christmas campaign`
- `One chair has broken wheel`

**❌ Avoid:**
- Information that should go in other fields
- Excessively long notes

**Rules:**
- Relevant additional information
- Use proper spelling
- Be concise but clear
- Don't repeat information from other fields

---

## 🤖 Using the Telegram Bot

### Example of CORRECT conversation:

**User:**
```
I want to add chairs
```

**Bot:**
```
Perfect, I'll help you register the chairs. Please provide the following 
information (only Code, Name and Quantity are required):

• Code (e.g., CHAIR-001)
• Item name
• Quantity
• Category
• Condition (new/used/good/fair/poor)
• Donor
• Date received (DD/MM/YYYY)
• Location
• Additional notes
```

**User:**
```
Code CHAIR-025
Name Ergonomic office chairs
Quantity 8
Category Furniture
Condition Good
Donor ABC Company
Date 01/14/2025
Location Warehouse B - Shelf 5
Notes Two have adjustable arms
```

**Bot:**
```
✅ Item successfully registered in inventory!

📦 Code: CHAIR-025
📝 Name: Ergonomic office chairs
📋 Category: Furniture
📊 Quantity: 8
🏷️ Condition: Good
📍 Location: Warehouse B - Shelf 5
```

---

## 📋 Checklist Before Registering

Before adding each item, verify:

- [ ] The code is unique (doesn't already exist)
- [ ] The code is in UPPERCASE
- [ ] The name is descriptive
- [ ] The quantity is a number
- [ ] The category is in the approved list
- [ ] The condition uses standard options
- [ ] The date uses DD/MM/YYYY format
- [ ] The location is specific
- [ ] I checked spelling

---

## 🚫 Common Errors to Avoid

1. **Duplicate codes** - Each item must have a unique code
2. **Inconsistent categories** - Always use the same name
3. **Incorrect date formats** - Always DD/MM/YYYY
4. **Spelling errors** - Check before sending
5. **Vague information** - Being specific helps later
6. **Mixing upper/lowercase** - Follow the document rules

---

## 💡 Final Tips

1. **Consistency is key** - Always use the same format
2. **Be specific** - More information is better than less
3. **Review before sending** - The bot doesn't correct errors
4. **Keep a catalog** - Have the list of categories and locations handy
5. **Update regularly** - Review inventory periodically

---

## 📊 Sample Data

### Option 1: Download CSV
You can download the CSV file with examples:
- [📥 Download sample-data.csv](../../ejemplos/datos-ejemplo.csv)

### Option 2: View in Google Sheets (Read-only)
For better interactive visualization:
- [📊 View examples in Google Sheets](#) *(https://docs.google.com/spreadsheets/d/1Ixam3gdp1Vk6bJ26bK2ITr550PXL1J0FdPOL1LwkV9Y/edit?usp=sharing)*

⚠️ **Note:** The Google Sheets is read-only for reference.

---

## 📞 Support and Resources

**Reference sheet (view only):**  
You can consult our reference sheet with examples at any time.

⚠️ **Do not modify this sheet** - it's for reference only. All items are added through the Telegram bot.

If you have questions about how to register a specific item, contact the system administrator.

---

**Last updated:** January 2025