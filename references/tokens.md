# Netcore — Full CSS Token Sheet

Paste the `:root` block into `index.css`. Also add the Google Fonts import above it.

```css
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@300;400;500;600;700&display=swap');

:root {
  /* === TYPEFACE === */
  --font-family: 'Manrope', system-ui, -apple-system, sans-serif;

  /* === TYPE SCALE (px sizes + line heights) === */
  --text-caption-s:   10px; --lh-caption-s:   18px;
  --text-caption-m:   12px; --lh-caption-m:   20px;
  --text-body-mid-s:  13px; --lh-body-mid-s:  21px;
  --text-body-mid-m:  14px; --lh-body-mid-m:  22px;
  --text-body-mid-l:  15px; --lh-body-mid-l:  23px;
  --text-body-lg-md:  16px; --lh-body-lg-md:  24px;
  --text-body-lg-lg:  18px; --lh-body-lg-lg:  26px;
  --text-heading-h3:  20px; --lh-heading-h3:  30px;
  --text-heading-h2:  22px; --lh-heading-h2:  32px;
  --text-heading-h1:  24px; --lh-heading-h1:  34px;
  --text-display-s:   28px; --lh-display-s:   38px;
  --text-display-m:   32px; --lh-display-m:   42px;
  --text-display-l:   36px; --lh-display-l:   46px;
  --text-display-xl:  40px; --lh-display-xl:  50px;

  --ls-body:    -0.01em;
  --ls-display: -0.015em;

  /* === FONT WEIGHTS === */
  --fw-light:    300;
  --fw-regular:  400;
  --fw-medium:   500;
  --fw-semibold: 600;
  --fw-bold:     700;

  /* === PRIMARY BLUE (brand) === */
  --blue-25:  #F6F8FF; --blue-50:  #EDF1FF; --blue-100: #D8E6FF;
  --blue-200: #AEBFFF; --blue-300: #7EA4FF; --blue-400: #4F7EF0;
  --blue-500: #3B71E8; --blue-600: #2F68E5; --blue-700: #1F51BE;
  --blue-800: #143A92; --blue-900: #0A2667; --blue-950: #07184A;

  /* === NEUTRAL GRAY (cool-tinted) === */
  --gray-25:  #FAFBFF; --gray-50:  #F5F6FA; --gray-100: #EBEBF5;
  --gray-200: #D9D9E8; --gray-300: #BBBBC8; --gray-400: #919198;
  --gray-500: #6B6B78; --gray-600: #50505D; --gray-700: #383845;
  --gray-800: #252530; --gray-900: #181820; --gray-950: #101018;

  /* === ERROR RED === */
  --red-25:  #FFF5F5; --red-50:  #FFEBE8; --red-100: #FECDCC;
  --red-200: #FDA29B; --red-300: #F97066; --red-400: #F04438;
  --red-500: #D92D20; --red-600: #C0201A; --red-700: #9A1B14;
  --red-800: #771510; --red-900: #540D0A; --red-950: #3C0807;

  /* === WARNING YELLOW (Untitled UI amber-yellow H=38-45°) === */
  --yellow-25:  #FFFDF5; --yellow-50:  #FFFAEB; --yellow-100: #FEF0C7;
  --yellow-200: #FEDF89; --yellow-300: #FEC84B; --yellow-400: #FDB022;
  --yellow-500: #F79009; --yellow-600: #DC6803; --yellow-700: #B54708;
  --yellow-800: #93370D; --yellow-900: #7A2E0E; --yellow-950: #4E1D09;

  /* === SUCCESS GREEN === */
  --green-25:  #F6FEF9; --green-50:  #ECFDF3; --green-100: #DCFAE6;
  --green-200: #ABEFC6; --green-300: #75E0A7; --green-400: #47CD89;
  --green-500: #17B26A; --green-600: #079455; --green-700: #067647;
  --green-800: #085D3A; --green-900: #053321; --green-950: #022113;

  /* === ACCENT ORANGE (logo colour only — not for warnings) === */
  --orange-25:  #FFF8F5; --orange-50:  #FFF0E8; --orange-100: #FFDCCC;
  --orange-200: #FFB799; --orange-300: #FF8C62; --orange-400: #FF6E35;
  --orange-500: #FF620C; --orange-600: #FC5E02; --orange-700: #D44600;
  --orange-800: #A63300; --orange-900: #762200; --orange-950: #511600;

  /* === SEMANTIC TEXT TOKENS === */
  --txt-primary:   #17173A;
  --txt-secondary: #6F6F8D;
  --txt-tertiary:  #9494AE;
  --txt-disabled:  #9494AE;
  --txt-brand:     #2F68E5;
  --txt-error:     #C0201A;
  --txt-warning:   #B54708;
  --txt-success:   #079455;
  --txt-inverse:   #FFFFFF;

  /* === BACKGROUNDS === */
  --bg-page:           #F4F8FF;
  --bg-surface:        #FFFFFF;
  --bg-subtle:         #FAFBFF;
  --bg-nav:            #291E30;
  --bg-disabled:       #FAFAFA;
  --bg-disabled-subtle:#F5F5F5;
  --bg-error:          #FFF5F5;
  --bg-warning:        #FFFAEB;
  --bg-success:        #F6FEF9;

  /* === BORDERS === */
  --border-default:  #D9D9E8;
  --border-hover:    #9898B0;
  --border-focus:    #2F68E5;
  --border-error:    #C0201A;
  --border-warning:  #DC6803;
  --border-success:  #079455;
  --border-disabled: #D4D4D4;

  /* === FOCUS RINGS === */
  --ring-brand:   0 0 0 4px rgba(47,104,229,0.15);
  --ring-error:   0 0 0 4px rgba(192,32,26,0.15);
  --ring-warning: 0 0 0 4px rgba(220,104,3,0.15);
  --ring-success: 0 0 0 4px rgba(7,148,85,0.15);

  /* === SHADOWS === */
  --shadow-xs:       0 1px 2px rgba(23,23,58,0.08);
  --shadow-sm:       0 1px 3px rgba(23,23,58,0.10);
  --shadow-md:       0 4px 8px rgba(23,23,58,0.12);
  --shadow-lg:       0 8px 24px rgba(23,23,58,0.14);
  --shadow-disabled: 0 1px 2px rgba(0,0,0,0.05);

  /* === BORDER RADIUS === */
  --radius-sm:      4px;
  --radius-md:      6px;
  --radius-default: 8px;
  --radius-lg:      12px;
  --radius-xl:      16px;
  --radius-pill:    999px;

  /* === SPACING === */
  --space-xs:  4px;
  --space-sm:  8px;
  --space-md:  12px;
  --space-lg:  16px;
  --space-xl:  24px;
  --space-2xl: 32px;
  --space-3xl: 48px;
}
```

## Tailwind config additions

```ts
// tailwind.config.ts
theme: {
  extend: {
    fontFamily: { sans: ['Manrope', 'system-ui', 'sans-serif'] },
    colors: {
      brand:   { DEFAULT: '#2F68E5', hover: '#4F7EF0', active: '#1F51BE', subtle: '#EDF1FF' },
      page:    '#F4F8FF',
      surface: '#FFFFFF',
      nav:     '#291E30',
    },
    borderRadius: {
      DEFAULT: '8px',
      lg:  '12px',
      xl:  '16px',
      pill:'9999px',
    },
    boxShadow: {
      xs: '0 1px 2px rgba(23,23,58,0.08)',
      sm: '0 1px 3px rgba(23,23,58,0.10)',
      md: '0 4px 8px rgba(23,23,58,0.12)',
      lg: '0 8px 24px rgba(23,23,58,0.14)',
    },
  }
}
```
