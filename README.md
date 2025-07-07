# Django issue #36168

This repo demonstrates a fix for [Django issue #36168](https://code.djangoproject.com/ticket/36168).
For a detailed solution to this issue: https://dev.to/houston_wong_78b96dd3a773/fixing-django-squashed-migration-in-multi-app-issue-36168-5g39

## ✅ What This Is

- Django version: 6.0.dev20250627185702
- Patch is in one file:

  django/db/migrations/executor.py

You can copy this file into your Django installation to apply the fix.

---

## 🛠 How to Use

1. Clone the repo:

   git clone https://github.com/vanschelven/squashwithrename.git
   
   cd squashwithrename

2. Copy the patched file over the original:

   cp django/db/migrations/executor.py <path-to-your-django>/db/migrations/executor.py

---

## ✅ To Verify the Fix

In the squashwithrename folder
Run:

   -rm db.sqlite3
   -python manage.py migrate
   -python manage.py migrate triggerfailingcode 0001_initial

With the fix, the last command should succeed without raising a FieldDoesNotExist error.

---

## 📄 Notes

This repo is not just for reproducing the bug — it provides a working patched executor for anyone who wants to understand or test the fix.
