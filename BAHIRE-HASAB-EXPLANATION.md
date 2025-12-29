# Bahire Hasab (ባሕረ ሓሳብ) - Ethiopian Calendar Calculation

## What is Bahire Hasab?

**Bahire Hasab** means "Sea of Thought" in Ge'ez. It's a 1,500+ year old Ethiopian Orthodox mathematical system to calculate:
- When Easter (ትንሳኤ) falls each year
- All movable fasting periods and feasts
- Fixed church holidays

## How It Works (Simplified)

### Step 1: Find Your Position in the 19-Year Cycle

The Ethiopian calendar uses the **Metonic Cycle** - a 19-year period where the moon phases align with the solar year.

```javascript
Year 2018 example:
Amete Alem = 2018 + 5500 = 7518 (years since Creation)
Medeb = 7518 % 19 = 1 (position in 19-year cycle)
```

### Step 2: Calculate the Lunar Offset

Each year, the lunar calendar "drifts" 11 days ahead of the solar calendar.

```javascript
Wenber = Medeb - 1 = 0
Abekte = (0 × 11) % 30 = 0 (lunar offset)
```

### Step 3: Find Beale Metikea (First Full Moon)

This is the **first full moon** after Ethiopian New Year (1 Meskerem).

```javascript
Beale Metikea Ken (day) = 30 - Abekte = 30 - 0 = 30
Beale Metikea Wor (month) = 0 (Meskerem)
```

So the full moon is on **30 Meskerem** in 2018.

### Step 4: Apply ELET_TEWSAK (Weekday Adjustment)

This is the **magic ingredient**! It ensures Easter always falls on Sunday.

```javascript
ELET_TEWSAK = [6, 5, 4, 3, 2, 8, 7]
              Mon Tue Wed Thu Fri Sat Sun
```

**Example:** If the full moon falls on **Wednesday**, add **4 days**. If it falls on **Saturday**, add **8 days**.

This adjustment accounts for the need to have Easter on Sunday.

### Step 5: Calculate Mebaja Hamer (Reference Point)

```javascript
Days to Mebaja Hamer =
  (Days to full moon) + 120 + ELET_TEWSAK[weekday of full moon]

For 2018:
= 30 + 120 + ELET_TEWSAK[Wed]
= 30 + 120 + 4
= 154 days from New Year
```

**Mebaja Hamer** = 154 days from 1 Meskerem = **15 Yekatit** (5th month, day 15)

### Step 6: Calculate All Movable Feasts

All fasting periods and movable feasts are calculated from Mebaja Hamer:

| Feast/Fast | Days from Mebaja Hamer | 2018 Example |
|------------|------------------------|--------------|
| **ጾመ ነነዌ** (Nineveh Fast) | 0 days | 15 Yekatit |
| **ዓብይ ጾም** (Great Lent) | +14 days | 29 Yekatit |
| **ደብረ ዘይት** (Palm Sunday) | +41 days | 20 Megabit |
| **ሆሳዕና** (Hosanna) | +48 days | 27 Megabit |
| **ስቅለት** (Good Friday) | +50 days | 29 Megabit |
| **ትንሳኤ** (Easter/Resurrection) | +52 days | 2 Miyaziya |

## Why ELET_TEWSAK is Important

The values in ELET_TEWSAK ensure:
1. **Easter is always on Sunday**
2. **Great Lent is always 55 days** before Easter
3. All other feasts maintain proper spacing

### Example: Why Different Values?

If the full moon is on:
- **Monday** → Add 6 days → Next Sunday
- **Saturday** → Add 8 days (1 week + 1 day) → Next Sunday after a full week
- **Sunday** → Add 7 days (1 full week) → Next Sunday

This prevents Easter from falling too close to the full moon and maintains the tradition of celebrating one week after.

## Fixed Feasts (Not Calculated)

Some feasts have **fixed dates** every year:

| Feast | Date | Gregorian Equivalent |
|-------|------|---------------------|
| **መስቀል** (Meskel) | 17 Meskerem | Sept 27 |
| **ልደት** (Christmas) | 29 Tahsas | Jan 7 |
| **ጥምቀት** (Timket/Epiphany) | 11 Tiri | Jan 19 |
| **ቅዱስ ዩሐንስ** (St. John) | 30 Nehassie | Sept 11 |

## Full 2019 Example Calculation

Let's calculate for **2019**:

```
1. Amete Alem = 2019 + 5500 = 7519
2. Medeb = 7519 % 19 = 2
3. Wenber = 2 - 1 = 1
4. Abekte = (1 × 11) % 30 = 11
5. Beale Metikea Ken = 30 - 11 = 19 (day)
6. Beale Metikea Wor = 0 (Meskerem)
   → Full moon on 19 Meskerem

7. Full moon falls on Friday
8. ELET_TEWSAK[Friday] = 2
9. Days to Mebaja Hamer = 19 + 120 + 2 = 141 days
10. 141 days from 1 Meskerem = 15 Yekatit

Result: ጾመ ነነዌ (Nineveh Fast) = 15 Yekatit 2019 ✓
```

## Why This System is Amazing

1. **100% Mathematical** - No need for astronomical observations
2. **Accurate for centuries** - Used for 1,500+ years
3. **Self-correcting** - The 19-year cycle keeps it synchronized
4. **Portable** - Priests could calculate holidays anywhere, even without books

## Key Formulas Summary

```javascript
// 1. World Era Year
ameteAlem(year) = year + 5500

// 2. Position in 19-year cycle
medeb(year) = ameteAlem(year) % 19

// 3. Lunar offset
abekte(year) = ((medeb(year) - 1) × 11) % 30

// 4. First full moon day
bealeMetikeaKen(year) = 30 - abekte(year)

// 5. Reference point for all movable feasts
daysEskeMebajaHamer(year) =
    bealeMetikeaKen(year) + 120 + ELET_TEWSAK[weekday]

// 6. All feasts calculated by adding days
neneweDate = daysEskeMebajaHamer(year) + 0
abiyTsomeDate = daysEskeMebajaHamer(year) + 14
tinsaeDate = daysEskeMebajaHamer(year) + 52
```

---

*This calculation system is one of the treasures of Ethiopian Orthodox Christianity, preserving ancient astronomical knowledge through pure mathematics.*
