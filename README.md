# Age Verification Plugin

This plugin provides age verification functionality using various methods including face scanning, BankID, MojeID, and document scanning.

## Setup

1. Create a Supabase project at [https://supabase.com](https://supabase.com)

2. Set up environment variables in `.env.local`:
```bash
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
NEXT_PUBLIC_HUGGINGFACE_API_KEY=your_huggingface_api_key
```

3. Run the SQL schema:
   - Navigate to the Supabase dashboard
   - Go to the SQL editor
   - Copy and paste the contents of `supabase/schema.sql`
   - Run the SQL commands to create the necessary tables and policies

4. Install dependencies:
```bash
npm install @supabase/supabase-js
```

## Usage

1. Create an e-shop record in the Supabase dashboard to get an API key

2. Integrate the plugin into your website:
```html
<iframe src="https://your-plugin-url?apiKey=your_api_key"></iframe>
```

## Development

1. Install dependencies:
```bash
npm install
```

2. Run the development server:
```bash
npm run dev
```

## Database Schema

### Eshops Table
- `id`: UUID (Primary Key)
- `api_key`: Text (Unique)
- `name`: Text
- `created_at`: Timestamp
- `updated_at`: Timestamp

### Verifications Table
- `id`: UUID (Primary Key)
- `eshop_id`: UUID (Foreign Key)
- `success`: Boolean
- `method`: Text
- `timestamp`: BigInt
- `user_id`: Text (Optional)
- `error`: Text (Optional)
- `created_at`: Timestamp
