<h1> How to add ranks to the Police Config</h1>


<ul>
  <li>Go to: wosa_jobs/job_data/police/police_config.lua</li>
  <li>Go to: Departments</li>
  <li> Pick the department you want add ranks to like i want to add SAST RANKS
    <ul>
      <li>Find the ranks</li>
      <li>then just copy and paste this</li>
       

  
    ['SAST - Test Rank'] = {
                Salary = Put how much this ranks gets,

                Management = true,
                UseGarage = true,
                ChangeOutfit = true,
                lockDoors = true,
                useMDT = true,
                getWeapons = true,
                useCameras = true,    <---- set up the permissons
                detectiveFeatures = true,
                Jail = true,

                ['Suit'] = true,
                ['Agent'] = true,
                ['Windbreaker'] = true,
                ['Winter Agent'] = true,
                ['Field Agent'] = true,                <---- set up the outfits
                ['Task Force'] = true,
                ['Special Reaction Team'] = true,

                weapons = {
                    {label = 'Combat Pistol', model = 'WEAPON_COMBATPISTOL', comps = {'COMPONENT_AT_PI_FLSH'}, ammo = 25},
                    {label = 'Pump Shotgun', model = 'WEAPON_PUMPSHOTGUN', comps = {'COMPONENT_AT_AR_FLSH'}, ammo = 15},
                    {label = 'Special Carbine', model = 'WEAPON_SPECIALCARBINE', comps = {'COMPONENT_AT_AR_FLSH', 'COMPONENT_AT_SCOPE_MEDIUM'}, ammo = 70},
                    {label = 'Marksman Rifle', model = 'WEAPON_MARKSMANRIFLE', comps = {}, ammo = 30},                <---- set up the Weapons
                },

                vehicles = {
                    'apoliceu',
                    'apoliceu6',
                    'apoliceu7',
                    'apoliceu9',            <---- set up the Cars
                    'apoliceu10',
                    'apoliceu13',
                    'apoliceu14',
                    'apoliceu15',
                    'apoliceub',
                }
            },
    </ul>
  </li>
  <li>then you done</li>
</ul> 
