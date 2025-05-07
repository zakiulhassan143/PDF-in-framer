# 📘 PDFPreview – Framer Code Component

The **PDFPreview** component lets you embed and display a PDF directly inside your Framer project using a Google Docs Viewer iframe. It’s perfect for showcasing documents, resumes, reports, eBooks, or any file you want to preview inside your design.

---

## ✨ Features

- 🖼️ **Live Preview of PDFs** using an embedded Google Docs Viewer
- 📐 Fully **responsive layout** that adapts to the frame size
- 🎨 Clean UI with border and rounded corners
- 🎛️ Framer property controls for easy customization
- ❤️ Credit note field built into the sidebar (for fun & personalization)

---

## 🧰 What You’ll Need

- A **Framer project** (free or paid)
- A **publicly accessible PDF URL** (hosted on Google Drive, Dropbox, or your own domain)

---

## 🔧 How to Install the Component

### Option 1: Manual Setup (Recommended for now)

1. Open your **Framer project**.
2. Go to the **Assets panel → Code** tab.
3. Click **➕ New Code Component**.
4. Name the component: `PDFPreview`
5. Replace the auto-generated code with the following full code block (⬇️ below).
6. Click **Save**.
7. Drag the `PDFPreview` component onto the canvas.
8. Paste your PDF link in the right-hand panel (under “PDF URL”).

---

## 🧪 PDFPreview Code (Copy-Paste This)

```tsx
import * as React from "react"
import { addPropertyControls, ControlType } from "framer"

type Props = {
    url: string
    note?: string
}

export function PDFPreview({ url }: Props) {
    return (
        <div
            style={{
                width: "100%",
                height: "100%",
                border: "1px solid #ccc",
                borderRadius: "12px",
                overflow: "hidden",
            }}
        >
            <iframe
                src={`https://docs.google.com/gview?url=${url}&embedded=true`}
                style={{ width: "100%", height: "100%" }}
                frameBorder="0"
                title="PDF Preview"
            />
        </div>
    )
}

// 👇 Property Panel Controls
addPropertyControls(PDFPreview, {
    url: {
        title: "PDF URL",
        type: ControlType.String,
        placeholder: "https://example.com/file.pdf",
    },
    note: {
        title: "📌",
        type: ControlType.Enum,
        options: ["Made with ❤️ by Zaki Ul Hassan"],
        optionTitles: ["Made with ❤️ by Zaki Ul Hassan"],
    },
})
