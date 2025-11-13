# Testing Checklist: Gray Text for Completed Items

## Quick Verification Guide

Use this checklist to quickly verify the gray text feature is working correctly.

---

## Pre-Testing Setup

- [ ] Dependencies installed (`npm install`)
- [ ] Application builds successfully (`npm run build`)
- [ ] Development server running (`npm run dev`)
- [ ] Browser opened to http://localhost:5173/

---

## Visual Tests

### Test 1: Basic Functionality
- [ ] Add a todo item to the list
- [ ] Item displays with **white text** when unchecked
- [ ] Click checkbox to mark as complete
- [ ] Item displays with **gray text (#999)** when checked
- [ ] Item displays with **line-through** decoration when checked

### Test 2: Multiple Items
- [ ] Add 3+ todo items to the list
- [ ] Check 1-2 items
- [ ] Verified: Checked items have gray text + line-through
- [ ] Verified: Unchecked items have white text only
- [ ] Verified: Each item is independent

### Test 3: Toggle Behavior
- [ ] Check an item (turns gray)
- [ ] Uncheck the same item (returns to white)
- [ ] Repeat 2-3 times
- [ ] Verified: State changes are immediate and consistent

### Test 4: Persistence
- [ ] Add several items, check some of them
- [ ] Note which items are checked (gray text)
- [ ] Refresh the page (F5)
- [ ] Verified: Previously checked items are still gray
- [ ] Verified: Previously unchecked items are still white
- [ ] Verified: Checkbox states match visual appearance

---

## Accessibility Tests

### Color Contrast
- [ ] Checked items use #999 text on #333 background
- [ ] Text is clearly readable
- [ ] Contrast ratio is approximately 5.9:1 (WCAG AA compliant)

### Screen Reader Compatibility
- [ ] Checkbox states are announced correctly
- [ ] Item text remains accessible
- [ ] No accessibility regressions

---

## Code Quality Tests

### CSS Implementation
- [ ] File modified: `src/css/style.css` only
- [ ] Selector used: `.item>input[type="checkbox"]:checked+label`
- [ ] Properties: `text-decoration: line-through;` and `color: #999;`
- [ ] No conflicts with other styles
- [ ] Follows BEM-like naming convention

### Build Quality
- [ ] No TypeScript compilation errors
- [ ] Build completes in reasonable time (<5 seconds)
- [ ] Bundle size increase is minimal

---

## Edge Cases

- [ ] Empty list (no items): No errors
- [ ] Single item: Works correctly
- [ ] All items checked: All display gray
- [ ] All items unchecked: All display white
- [ ] Rapid clicking: No visual glitches

---

## Performance

- [ ] No delays when checking/unchecking items
- [ ] No browser console errors
- [ ] No memory leaks after extended use
- [ ] Page loads quickly

---

## Browser Compatibility (Optional Extended Testing)

- [ ] Chrome/Chromium: Works correctly
- [ ] Firefox: Works correctly (if available)
- [ ] Safari: Works correctly (if available)
- [ ] Edge: Works correctly (if available)

---

## Regression Testing

- [ ] Adding new items still works
- [ ] Deleting items still works
- [ ] Clear button still works
- [ ] localStorage persistence still works
- [ ] No existing features broken

---

## Final Verification

- [ ] Feature meets original requirements
- [ ] No visual bugs or glitches
- [ ] Accessibility standards maintained
- [ ] Code follows project conventions
- [ ] All test cases passed

---

## Test Results

**Date Tested**: _________________  
**Tested By**: _________________  
**Status**: [ ] PASSED  [ ] FAILED  [ ] NEEDS REVIEW

**Notes**:
_________________________________________________________________
_________________________________________________________________
_________________________________________________________________

---

## Quick Test Script

For rapid verification, run through this 2-minute test:

1. Start dev server: `npm run dev`
2. Open http://localhost:5173/
3. Add 3 items: "Task 1", "Task 2", "Task 3"
4. Check "Task 2" → Should turn gray with line-through
5. Refresh page → "Task 2" should still be gray
6. Uncheck "Task 2" → Should return to white
7. ✅ If all steps work, feature is verified!

---

**Checklist Version**: 1.0  
**Last Updated**: November 13, 2025
