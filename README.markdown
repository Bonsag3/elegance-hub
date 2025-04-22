# Elegance Hub Website

A luxurious fashion boutique website for *Elegance Hub*, built with Netlify and Netlify CMS. This guide is for non-coders to set up, deploy, and manage the website for product presentation.

## Project Structure
- `index.html`: The user page with a hero, gallery, products, about, and contact sections.
- `styles.css`: Custom CSS styles.
- `static/admin/index.html`: Admin page for accessing Netlify CMS.
- `static/admin/config.yml`: CMS configuration for managing products.
- `content/products/`: Folder for product data (managed via CMS).
- `static/images/uploads/`: Folder for product images uploaded via CMS.

## Sample Products
The user page includes these sample products for presentation:
- Women’s Silk Dress: $299.00 (Elegant silk dress for evening wear)
- Men’s Tailored Suit: $499.00 (Sharp, tailored suit for formal occasions)
- Leather Handbag: $199.00 (Stylish leather bag for everyday elegance)
- Men’s Leather Shoes: $249.00 (Polished leather shoes for any occasion)

## How to Launch the Website on Netlify
Follow these steps to upload files and deploy the website. No coding is required.

### Step 1: Create a GitHub Account
1. Go to [github.com](https://github.com) and sign up for a free account.
2. Verify your email address.

### Step 2: Create a New Repository
1. Log into GitHub and click the “+” icon in the top-right corner, then select “New repository”.
2. Name the repository (e.g., `elegance-hub`).
3. Set it to “Public” and check “Add a README file”.
4. Click “Create repository”.

### Step 3: Upload the Files
1. Download the following files to your computer:
   - `index.html`
   - `styles.css`
   - `static/admin/index.html`
   - `static/admin/config.yml`
2. In your GitHub repository, click “Add file” > “Upload files”.
3. Create the folder structure by uploading files to the correct paths:
   - Drag `index.html` and `styles.css` to the root of the repository.
   - Create a `static` folder:
     - Click “Create new file”, name it `static/.gitkeep`, and commit it (this ensures the folder is created).
     - Inside `static`, create an `admin` folder and upload `index.html` and `config.yml` to `static/admin/`.
   - Create a `content` folder:
     - Click “Create new file”, name it `content/.gitkeep`, and commit it.
     - Inside `content`, create a `products` folder with a `.gitkeep` file.
4. Click “Commit changes” after each upload to save.

Your repository structure should look like this:
```
elegance-hub/
├── index.html
├── styles.css
├── static/
│   ├── admin/
│   │   ├── index.html
│   │   ├── config.yml
│   ├── images/
│   │   ├── uploads/
│   │   │   ├── .gitkeep
├── content/
│   ├── products/
│   │   ├── .gitkeep
```

### Step 4: Create a Netlify Account
1. Go to [netlify.com](https://www.netlify.com) and sign up for a free account (use your email or GitHub account).
2. Verify your email address.

### Step 5: Deploy the Site on Netlify
1. Log into Netlify and click “New site from Git”.
2. Select “GitHub” and authorize Netlify to access your repositories.
3. Choose your `elegance-hub` repository.
4. Configure the deploy settings:
   - **Branch**: `main`
   - **Build command**: Leave blank (no build process needed).
   - **Publish directory**: `/` (root directory).
5. Click “Deploy site”.
6. Netlify will assign a temporary URL (e.g., `random-name.netlify.app`). You can change it later in “Site settings” > “Change site name”.

### Step 6: Enable Netlify CMS
1. In your Netlify dashboard, go to your site and click “Identity” at the top.
2. Click “Enable Identity”.
3. Under “Settings” > “Identity” > “Git Gateway”, click “Enable Git Gateway”.
4. Invite yourself as a user:
   - Go to “Identity” > “Invite users” and enter your email.
   - Check your email for an invitation, click the link, and set a password.

### Step 7: Enable the Contact Form
1. In your Netlify dashboard, go to “Forms” and ensure the contact form is detected (it’s included in `index.html` with `data-netlify="true"`).
2. If not detected, go to “Site settings” > “Forms” and verify that form submissions are enabled.
3. Test the form by submitting it at `your-site.netlify.app/#contact`. Submissions will appear in “Forms” > “Form submissions”.

### Step 8: Test the Website
1. Visit `your-site.netlify.app` to see the user page with the gallery, products, and other sections.
2. Go to `your-site.netlify.app/admin` to access the admin panel.
3. Click “Open Product Manager”, log in with your Netlify Identity email and password, and test adding a product:
   - Click “Products” > “New Product”.
   - Enter details (e.g., “Summer Blazer”, $349.00, upload an image, select “Men”, check “Feature on Homepage”).
   - Click “Save” and “Publish”.

### Step 9: Update Products for Presentation
- Products added via CMS are saved in `content/products/` as markdown files (e.g., `summer-blazer.md`).
- To display them on the user page, manually update `index.html`:
  1. Copy the product details from the CMS (e.g., image URL from `/images/uploads/`).
  2. Edit `index.html` in GitHub’s web interface:
     - Add a new product card to the `#products` section:
       ```html
       <div class="bg-white shadow-md rounded-lg overflow-hidden">
         <img src="/images/uploads/summer-blazer.jpg" alt="Summer Blazer" class="w-full h-64 object-cover">
         <div class="p-4">
           <h3 class="text-lg font-semibold text-gray-900">Summer Blazer</h3>
           <p class="text-gray-600">$349.00</p>
           <p class="text-sm text-gray-500">Lightweight linen blazer for warm weather.</p>
           <a href="#" class="mt-4 inline-block bg-gray-900 text-white px-4 py-2 rounded hover:bg-gray-700">View Details</a>
         </div>
       </div>
       ```
     - If “Feature on Homepage” is checked, add the product to the `#gallery` section:
       ```html
       <div class="relative">
         <img src="/images/uploads/summer-blazer.jpg" alt="Summer Blazer" class="w-full h-64 object-cover rounded">
         <span class="absolute top-2 left-2 bg-red-600 text-white text-xs px-2 py-1 rounded">Featured</span>
       </div>
       ```
  3. Commit changes in GitHub, and Netlify will redeploy the site.

## Tips for Non-Coders
- **Image Uploads**: Use high-quality JPG or PNG images (under 2MB) for products. Upload via the CMS for automatic storage in `/images/uploads/`.
- **Editing Products**: In the CMS, click “Products” to view, edit, or delete items.
- **Customizing Presentation**:
  - Change the hero image in `index.html` (edit the `style="background-image: url(...)"` line).
  - Update product descriptions in the `#products` section for richer presentation.
- **Need Help?**: Visit [docs.netlify.com](https://docs.netlify.com) or contact a developer for advanced features (e.g., dynamic product display).

## Notes
- The gallery and products sections use sample images from Unsplash. Replace with your own via the CMS.
- The contact form is functional with Netlify Forms. Check submissions in the Netlify dashboard.
- To display CMS products automatically, hire a developer to integrate a static site generator like Hugo.
- For e-commerce (e.g., payments), consult a developer to add Shopify or Snipcart.