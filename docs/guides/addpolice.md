<h1> Add Police Department </h1>

<ol>
  <li>first go to wosa_jobs/job_data/police/police_config.lua</li>
  <li>look for Department data then do this as the pics follow</li>
  <li>then go down to Departments then put</li>
  

    [name here] = {
       ['Name here - Rank Here'] = {
                Salary = How much you want them get paid,

                Management = true,
                UseGarage = true,
                ChangeOutfit = true,
                lockDoors = true,
                useMDT = true,
                getWeapons = true,
                useCameras = true,
                detectiveFeatures = true,
                Jail = true,

                ['Suit'] = true,
                ['Agent'] = true,
                ['Windbreaker'] = true,
                ['Winter Agent'] = true,
                ['Field Agent'] = true,
                ['Task Force'] = true,
                ['Special Reaction Team'] = true,

                weapons = {
                    {label = 'Combat Pistol', model = 'WEAPON_COMBATPISTOL', comps = {'COMPONENT_AT_PI_FLSH'}, ammo = 25},
                    {label = 'Pump Shotgun', model = 'WEAPON_PUMPSHOTGUN', comps = {'COMPONENT_AT_AR_FLSH'}, ammo = 15},
                    {label = 'Special Carbine', model = 'WEAPON_SPECIALCARBINE', comps = {'COMPONENT_AT_AR_FLSH', 'COMPONENT_AT_SCOPE_MEDIUM'}, ammo = 70},
                },

                vehicles = {
                    'Spawn name goes here',
                }
    },
</ol>
