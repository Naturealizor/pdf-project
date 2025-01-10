<!-- MixerDocs.svelte -->
<script lang="ts">
  interface YouTubeLink {
    title: string;
    url: string;
  }

  interface DocumentSection {
    title: string;
    overview: string[];
    ytlinks?: YouTubeLink[];
    suppliesintro?: string[];
    supplies?: Array<{
      name: string;
      description?: string;
      url: string;
    }>;
    pdfUrl: string;
  }

  // Type the selectedDoc
  type DocumentKey = 'k5a' | 'pro600' | 'pro6000hd' | 'tilthead' | 'beater' | 'serial';
  let selectedDoc: DocumentKey = $state('k5a');
  
  const documents: Record<DocumentKey, DocumentSection> = {
    k5a: {
      title: 'K5A/K5SS/KSM5/KM50/KSMC50',
      overview: [
        'All K5A/K5SS models are of the same family and use all of the same internal components and the main difference between the models are the trim packages associated with each, for example some models may have on overload reset, and some may be rated for commercial use. If you have a K5SS/K5A, the following videos will be helpful for servicing, diagnosing and repairing your machine! We discuss all of the gears and supplies in the video series, we show the full disassembly of the gears/transmission parts and supplies will be linked below! Reference the Tilt Head rear end and electrical component guide for tuning and replacing parts in the rear end as the electronics are identical.',
        
      ],
      ytlinks: [
        {
          title: 'Regrease Pt. 1/3',
          url: 'https://youtu.be/20-UJD_asKA'
        },
        {
          title: 'Regrease Pt. 2/3',
          url: 'https://youtu.be/h2RY-q6JQQw'
        },
        {
          title: 'Regrease Pt. 3/3',
          url: 'https://youtu.be/AhyYUva2bgo'
        }
      ],
      suppliesintro: [
        'By purchasing parts through Mr. Mixer you get not only the full length highly detailed walkthrough videos but you also have direct access to Mr. Mixer and team for questions and issues that may arise during your repair. The knowledge provided is top notch to ensure your repairs and service goes seamlessly. We offer an unparalleled customer service experience.',
        'Grease', 
        'The Grease provided by Mr. Mixer is NSF H1 NLGI2 Food safe! We have done the research for you, this is the best grease available on the market for food safe machines. Grease can be obtained from a multitude of sources, however if you aren’t shopping with us you will be getting sold the cheapest grease available which is an NLGI 1. The NLGI scale is a rating of viscosity, the NLGI1 is more fluid like and is prone to breaking down and leaking faster as well as it does not adhere to the gears as well as the NLGI 2 which means your machine will be susceptible to excess frictions and damage.'
      ],
      supplies: [
        {
          name: 'NSF H1 NLGI 2 Food Safe Grease',
          url: 'https://www.mrmixer.store/store-2den3/p/yhnwsrjcxcw0t2oaigs2ylh89p9pqi'
        },
        {
          name: 'NSF H1 NLGI 2 Food Safe Grease W/ Gasket',
          description: 'Mr. Mixer Manufactured W/ Highest quality gasket material',
          url: 'https://www.mrmixer.store/store-2den3/p/gid2z7irohaouqfax414780saa90zc'
        },
        {
          name: 'Tilt Head Gasket',
          description: 'Mr. Mixer Manufactured W/ Highest quality gasket material',
          url: 'https://www.mrmixer.store/store-2den3/p/6t5ctejirx9rj7laofiv2lzdhoms4p'
        },
        {
          name: 'Mr Mixer Re-Grease Kit',
          description: 'Includes Mallet/Scrapers/Gloves/Tool Box',
          url: 'https://www.mrmixer.store/store-2den3/p/2fjgsacchn2qo5jjqxd0qt9xv2ttbk'
        },
        {
          name: 'Metal Grease Pick Scraper',
          description: 'Designed to get into the tight crevices for maximum grease removal',
          url: 'https://www.mrmixer.store/store-2den3/p/0flyabijjpxfrbjuzl9xgv9q7ihtjh'
        },
        {
          name: 'Pin Punches',
          description: 'For removal of planetary and worm gear groove pins',
          url: 'https://www.mrmixer.store/store-2den3/p/zw4b8fc2wk9g4xkx9pwfb0bdj4pnph'
        },
        {
          name: 'O-ring and Washer Replacements',
          url: 'https://www.mrmixer.store/store-2den3/p/replacement-washer-and-o-ring-kit'
        },
        {
          name: 'Factory Replacement Worm Gear',
          description: 'OEM Whirlpool Direct, be wary of amazon/third party gears',
          url: 'https://www.mrmixer.store/store-2den3/p/5qx3tt8knkavd73vvwc7ms5z2jjreb'
        },
        {
          name: 'Worm Gear Assembly',
          description: 'For faster replacement, no punches required',
          url: 'https://www.mrmixer.store/store-2den3/p/worm-gear-assembly'
        },
        {
          name: 'Center Gear/Main Gear',
          url: 'https://www.mrmixer.store/store-2den3/p/center-gear-tilt-head-mixers'
        },
        {
          name: 'Hub Gear',
          url: 'https://www.mrmixer.store/store-2den3/p/hub-gear-all-models'
        },
        {
          name: 'Pinion Shaft Gear',
          url: 'https://www.mrmixer.store/store-2den3/p/pinion-shaft-gear-tilt-heads-k5ak5ss-style-bowl-raise'
        },
        {
          name: 'Complete Gear Set',
          description: 'All of the above gears for a full rebuild of the gearbox',
          url: 'https://www.mrmixer.store/store-2den3/p/complete-gear-replacement-all-tilt-headsk5ss-style-machines'
        }
      ],
      pdfUrl: '/docs/k5a-manual.pdf'
    },
    pro600: {
      title: 'Professional 600/Pro 5+/Professional HD',
      overview: [
        'All of the above models are of the same family and use all of the same internal components. Over the years there have been a few variations of parts, but the overall design is identical. If you have a Professional Bowl Lift Model the following videos will be helpful for servicing, diagnosing and repairing your machine! We discuss all of the gears and supplies in the video series, we show the full disassembly of the gears/transmission parts and supplies will be linked below!'
      ],
      pdfUrl: '/docs/pro600-manual.pdf'
    },
    pro6000hd: {
      title: 'Professional 6000HD, Proline 7Qt, and 8Qt Commercial',
      overview: [
        'All of the DC powered models are of the same family and use all of the same internal components and the main difference between the models are the trim packages associated with each, for example the 6000hd has the tulip bowl, and the 8qt is rated for commercial use. If you have the above mentioned units the following videos will be helpful for servicing, diagnosing and repairing your machine! We discuss all of the gears and supplies in the video series, we show the full disassembly of the gears/transmission parts and supplies will be linked below! There are some minor discrepancies in the electronics (different speed board, they will be linked below).'
      ],
      pdfUrl: '/docs/pro6000hd-manual.pdf'
    },
    tilthead: {
      title: 'Tilt Head Models (Artisan/Classic/UltraPower/Classic Plus/Deluxe)',
      overview: [
        'All tilt head models are of the same family and use all of the same internal components and the main difference between the models are the trim packages associated with each, for example the Artisan (comes with a 5qt bowl, a larger variety of color and things such as a handle on the bowl) The Classic (4.5 qt bowl, can have a handle but generally not, this is the base version of the tilt head machines). If you have a tilt head, the following videos will be helpful for servicing, diagnosing and repairing your machine! We discuss all of the gears and supplies in the video series, we show the full disassembly of the gears/transmission parts and supplies will be linked below! Reference the Tilt Head rear end and electrical component guide for tuning and replacing parts in the rear end!'
      ],
      pdfUrl: '/docs/tilthead-manual.pdf'
    },
    beater: {
      title: 'Beater Blade Guide',
      overview: [
        'Beater Blade was the first paddle with a proprietary soft plastic edge.',
        'Features a powder coated metal frame and high quality soft plastic edges.',
        'Designed with a helical contour for optimal bowl contact.'
      ],
      pdfUrl: '/docs/beater-guide.pdf'
    },
    serial: {
      title: 'Serial Number Guide',
      overview: [
        'Serial numbers contain manufacturing location, year, week, and unit number.',
        'Year codes recycle every 30 years.',
        'Week codes range from 00-52, starting with first Monday of the year.'
      ],
      pdfUrl: '/docs/serial-guide.pdf'
    }
  };
</script>
  
  <div class="w-full max-w-4xl mx-auto p-4">
    <div class="bg-white rounded-lg shadow-lg">
      <div class="p-6 border-b border-gray-200">
        <h1 class="text-2xl font-bold">KitchenAid Mixer Documentation</h1>
      </div>
      
      <div class="flex flex-col md:flex-row gap-4 p-6">
        <!-- Navigation -->
        <nav class="w-full md:w-64 space-y-2">
          {#each Object.entries(documents) as [key, doc]}
            <button
              onclick={() => selectedDoc = key}
              class="w-full text-left px-4 py-2 rounded-lg transition-colors
                {selectedDoc === key 
                  ? 'bg-blue-100 text-blue-700' 
                  : 'hover:bg-gray-100'}"
            >
              {doc.title}
            </button>
          {/each}
        </nav>
  
        <!-- overview -->
        <div class="flex-1 p-4 bg-gray-50 rounded-lg">
          <h2 class="text-xl font-semibold mb-4">
            {documents[selectedDoc].title}
          </h2>
          <div class="space-y-4">
            {#each documents[selectedDoc].overview as paragraph}
              <p class="text-gray-700">{paragraph}</p>
            {/each}
            {#if documents[selectedDoc].ytlinks}
              {#each documents[selectedDoc].ytlinks! as link}
                <a href={link.url} target="_blank" class="text-blue-500 flex flex-row items-center gap-2"><img url='https://commons.wikimedia.org/wiki/File:YouTube_social_white_square_(2017).svg' alt="YouTube" class="w-4 h-4" />{link.title}</a>
              {/each}
            {/if}
          </div>
          
          <!-- Added PDF download link at bottom of overview -->
          {#if documents[selectedDoc].pdfUrl}
            <div class="mt-6">
              <a 
                href={documents[selectedDoc].pdfUrl} 
                target="_blank" 
                class="inline-flex items-center px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition-colors"
              >
                <span>Download PDF Manual</span>
              </a>
            </div>
          {/if}
        </div>
      </div>
    </div>
  </div>
  
  <style>
    /* Any additional component-specific styles can go here */
  </style>